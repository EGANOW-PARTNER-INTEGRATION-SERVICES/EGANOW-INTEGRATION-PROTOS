================================
GHIPSS credentials on Key Vault
================================

```go
package configs

type KeystoreConfig struct {
	// server
	GrpcServerPort string // from env
	GrpcServerHost string // from env
	HttpServerPort string // from env
	HttpServerHost string // from env
	
	//base url
	BaseUrl string // from env
	
	// environment
	IsProduction bool // set up in the loadFromEnv function
	
	// database
	PublicDbConnUrl   string `opitem:"PUBLIC_PAY_PARTNER_TRANSACTION_DB_URL" opfield:"server"`
	LocalDbConnUrl    string `opitem:"LOCAL_PAY_PARTNER_TRANSACTION_DB_URL" opfield:"server"`
	DbConnUrl         string
	DataSourceTimeout time.Duration
	
	// cache
	RedisHost     string `opitem:"GHIPSS_TRANSACTION_REDIS" opfield:"host"`
	RedisPort     string `opitem:"GHIPSS_TRANSACTION_REDIS" opfield:"port"`
	RedisPassword string `opitem:"GHIPSS_TRANSACTION_REDIS" opfield:"password"`
	
	// partner credentials
	BasicAuthUsername  string `opitem:"GHIPSS_BASIC_AUTH" opfield:"username"`
	BasicAuthPassword  string `opitem:"GHIPSS_BASIC_AUTH" opfield:"credential"`
	EganowPayPartnerId string `opitem:"GHIPSS_PAY_PARTNER_ID" opfield:"password"`
	
	// @todo -> add the remaining fields below
}

```
=================
.env
=================

```.dotenv
TSQ_BASE_URL=https://172.27.30.29/SwitchGIP/WSGIP?wsdl
BASE_URL=https://172.27.30.72/SwitchGIP/WSGIP?wsdl
GRPC_SERVER_PORT=443
GRPC_SERVER_HOST=
HTTP_SERVER_PORT=80
HTTP_SERVER_HOST=
ENV=dev
OP_CONNECT_HOST=http://credentials.eganowapi.net
OP_CONNECT_TOKEN=eyJhbGciOiJFUzI1NiIsImtpZCI6ImplZ3dqZ2V5N20ybXhqa2ZxdHV3dmU2aGdtIiwidHlwIjoiSldUIn0.eyIxcGFzc3dvcmQuY29tL2F1dWlkIjoiRVRBNVhCNEhPQkZHWk1MU1ZMTDZIRENXVTQiLCIxcGFzc3dvcmQuY29tL3Rva2VuIjoiUXdEanB5TEJMYWl3dTRMYllQWG1JQk5PQWZNdGFnMVEiLCIxcGFzc3dvcmQuY29tL2Z0cyI6WyJ2YXVsdGFjY2VzcyJdLCIxcGFzc3dvcmQuY29tL3Z0cyI6W3sidSI6ImF1MnVtdnF6NzJqdjVvbmljbXRpZDVjejQ0IiwiYSI6NDh9XSwiYXVkIjpbImNvbS4xcGFzc3dvcmQuY29ubmVjdCJdLCJzdWIiOiJWREpGWEYzRVhCSDNYTEpBTDZNQlJDWEFMVSIsImV4cCI6MTcxMDgwNjM5OSwiaWF0IjoxNzA4MTk1MjQ1LCJpc3MiOiJjb20uMXBhc3N3b3JkLmI1IiwianRpIjoidG5tN3VlNjN4Y3hnaXQ2aGc2aHIzMnNnNmkifQ.7rzKxwPRxeHMdhw7HUaUyBus9v7nbpNkQtb7ygnMJ08jiKTu-NQuBG25cjiubfbrqEm74GTJ352WkQNoUAC2ww
OP_VAULT=au2umvqz72jv5onicmtid5cz44
```