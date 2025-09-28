# Commandline

## Usage

### Krynetic.Database [command] [options]

### **Options**

`-sd`, `--storage-directory` `<storage-directory>`  
&nbsp;&nbsp;&nbsp;&nbsp;*Path to the storage directory*

`--license-file` `<license-file>` **(REQUIRED)**  
&nbsp;&nbsp;&nbsp;&nbsp;*Path to the license file*  


`-sh`, `--shell`  
&nbsp;&nbsp;&nbsp;&nbsp;*Enables shell*  
&nbsp;&nbsp;&nbsp;&nbsp;_default:_ **False**

`-s`, `--server` **(REQUIRED)**  
&nbsp;&nbsp;&nbsp;&nbsp;*Servers to start*  
<sub>
&nbsp;&nbsp;&nbsp;&nbsp;**Announce | Couchbase | CouchDB** \
&nbsp;&nbsp;&nbsp;&nbsp;**FTP | GraphQL | GRPC | Kafka** \
&nbsp;&nbsp;&nbsp;&nbsp;**MongoDB | MQTT | OData** \
&nbsp;&nbsp;&nbsp;&nbsp;**OpenAPI | Redis | S3 |** \
&nbsp;&nbsp;&nbsp;&nbsp;**SocketIO | SQL | SSH | WCF**
</sub>

`--prefill`  
&nbsp;&nbsp;&nbsp;&nbsp;*Prefills the database with dummy data for DEBUG*  
&nbsp;&nbsp;&nbsp;&nbsp;_default:_ **False**

`-ot`, `--opentelemetry` `<opentelemetry>`  
&nbsp;&nbsp;&nbsp;&nbsp;*Configure an OpenTelemetry server to use*

`--version`  
&nbsp;&nbsp;&nbsp;&nbsp;*Show version information*

`-?`, `-h`, `--help`  
&nbsp;&nbsp;&nbsp;&nbsp;*Show help and usage information*

---

### **Commands**

`-h`, `--help`  
&nbsp;&nbsp;&nbsp;&nbsp;*Display help info*

---

## Example usage

**Krynetic.Database** \
&nbsp;&nbsp;**--license-file** "/path/to/license.lic" \
&nbsp;&nbsp;**--storage-directory** "/data/store" \
&nbsp;&nbsp;**--server** MQTT \
&nbsp;&nbsp;**--server** GraphQL \
&nbsp;&nbsp;**--server** SocketIO \
&nbsp;&nbsp;**--opentelemetry** "http://otel.company.com:4317"

*Starts three servers MQTT, GraphQL and SocketIO, which also reports telemetry*