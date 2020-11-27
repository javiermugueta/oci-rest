# ocirest
bash wrapper for OCI REST API
## setup instructions
clone this repo<p>
```
git clone https://github.com/javiermugueta/ocirest
cd ocirest
chmod 700 oci-rest samples.sh
 ```
put your env data in <b>my-oci-env</b> file <p>
try some samples with <b>samples.sh</b>
## execution
```
oci-rest <api-endpoint-without-protocol> <verb> <method>
```
Example<p>
```
./oci-rest objectstorage.eu-frankfurt-1.oraclecloud.com get "/n/"
```
## troubleshooting
### You get this:
```
{
  "code" : "NotAuthorizedOrNotFound",
  "message" : "Authorization failed or requested resource not found."
}
```
Reason: Typo error in the method
### You get this:
```
{
  "code" : "NotAuthenticated",
  "message" : "The required information to complete authentication was not provided or was incorrect."
}
```
Reason: error in my-oci-env data