# ocirest
bash wrapper for OCI REST API
## setup instructions
clone this repo<p>
```
git clone https://github.com/javiermugueta/oci-rest.git
cd ocirest
chmod 700 oci-rest samples.sh
 ```
put your env data in <b>my-oci-env</b> file <p>
try some samples with <b>samples.sh</b><p>
OCI REST API: https://docs.cloud.oracle.com/en-us/iaas/api/<p>
## execution
```
oci-rest <api-endpoint-without-protocol> [<file with json body for post verb>] <verb> <method>
```
Example 1<p>
```
./oci-rest objectstorage.eu-frankfurt-1.oraclecloud.com get "/n/"
```
Example 2<p>
```
cat <<EOF > body.json
{
	"granularity": "HOURLY",
	"tenantId": "ocid1.tenancy.oc1..aaaaaaaaei...",
	"timeUsageStarted": "2021-02-10T00:00:00.000Z",
	"timeUsageEnded": "2021-02-11T00:00:00.000Z"
}
EOF
./oci-rest usageapi.eu-frankfurt-1.oci.oraclecloud.com post body.json "/20200107/usage"
```
## troubleshooting
### You get this:
```
{
  "code" : "NotAuthorizedOrNotFound",
  "message" : "Authorization failed or requested resource not found."
}
```
Reason: Typo error in the method or, if correct, you don't have permissions to use the endpoint
### You get this:
```
{
  "code" : "NotAuthenticated",
  "message" : "The required information to complete authentication was not provided or was incorrect."
}
```
Reason: error in my-oci-env data
