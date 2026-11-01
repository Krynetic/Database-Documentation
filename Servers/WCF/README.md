# WCF (SOAP)

**WSDL:** <http://localhost:8086/DictionaryService?wsdl> · **Server name:** `WCF` · **Ports:** `8086` (HTTP, SOAP 1.2), `8090` (TCP)

```bash
Krynetic.Database --server WCF
```

Change the SOAP namespace if your clients expect another:

```bash
Krynetic.Database --server WCF --server-config WCF namespace "urn:MyCompany"
```

## Service contract

```csharp
[ServiceContract(Namespace = "urn:KryneticWCF")]
public interface IDictionaryService
{
    /// <summary>Set data at given key</summary>
    /// <param name="key"></param>
    /// <param name="json">JSON string</param>
    [OperationContract(Action = "urn:KryneticWCF/Set", ReplyAction = "urn:KryneticWCF/SetResponse")]
    void Set(string key, [StringSyntax(StringSyntaxAttribute.Json)] string? json);

    /// <summary>Get data at given key</summary>
    /// <param name="depth">JSON serialization depth</param>
    /// <returns>JSON string</returns>
    [OperationContract(Action = "urn:KryneticWCF/Get", ReplyAction = "urn:KryneticWCF/GetResponse")]
    string? Get(string key, int? depth);
}
```

| Operation | Parameters | Result |
|---|---|---|
| `Set` | `key` (path), `json` (a JSON document as a string) | none |
| `Get` | `key` (path), `depth` (optional: how many levels of the JSON tree to return) | A JSON document as a string, or null |

## Client configuration

Use a SOAP 1.2 custom binding with text message encoding over HTTP:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <system.serviceModel>
        <bindings>
            <customBinding>
                <binding name="IDictionaryServiceSoapBinding" sendTimeout="00:05:00">
                    <textMessageEncoding messageVersion="Soap12" />
                    <httpTransport />
                </binding>
            </customBinding>
        </bindings>
        <client>
            <endpoint address="http://localhost:8086/DictionaryService" binding="customBinding"
                bindingConfiguration="IDictionaryServiceSoapBinding" contract="IDictionaryService"
                name="IDictionaryServiceSoapPort" />
        </client>
    </system.serviceModel>
</configuration>
```

## Generate a client

.NET with `dotnet-svcutil`:

```bash
dotnet tool install --global dotnet-svcutil
dotnet-svcutil http://localhost:8086/DictionaryService?wsdl
```

Then call the generated client:

```csharp
await client.SetAsync("/blog/title", "\"My blog\"");
var json = await client.GetAsync("/blog", depth: 2);
```

`Set` expects a valid JSON document, so a string value needs its quotes (`"\"My blog\""`).

## Operations through WCF

[Operations](../../Operations.md) are JSON objects, so they can be sent as the `json` argument:

```csharp
await client.SetAsync("/number1", "{\"_op\":\"increment\",\"value\":3}");
```
