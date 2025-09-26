# Krynetic WCF

### `Default Endpoint` 
#### [http://localhost:8086/DictionaryService?wsdl](http://localhost:8086/DictionaryService?wsdl)

#### Example config

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
            <endpoint address="http://localhost/DictionaryService" binding="customBinding"
                bindingConfiguration="IDictionaryServiceSoapBinding" contract="IDictionaryService"
                name="IDictionaryServiceSoapPort" />
        </client>
    </system.serviceModel>
</configuration>
```

### `IDictionaryService` Contract

```csharp
[ServiceContract(Namespace = "urn:KryneticWCF")]
public interface IDictionaryService
{
    /// <summary>
    /// Set data at given key
    /// </summary>
    /// <param name="key"></param>
    /// <param name="json">JSON string</param>
    [OperationContract(Action = "urn:KryneticWCF/Set", ReplyAction = "urn:KryneticWCF/SetResponse")]
    void Set(string key, [StringSyntax(StringSyntaxAttribute.Json)] string? json);

    /// <summary>
    /// Get data as given key
    /// </summary>
    /// <param name="depth">JSON serialization depth</param>
    /// <returns>JSON string</returns>
    [OperationContract(Action = "urn:KryneticWCF/Get", ReplyAction = "urn:KryneticWCF/GetResponse")]
    string? Get(string key, int? depth);
}
```
