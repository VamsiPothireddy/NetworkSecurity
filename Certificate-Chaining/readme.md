


# How Digital Certs are created? 
Lets say Im the owner of website example.com and want consumers of this website feel secure when they access website . Then I create pubkey and private keys using openssl or any other library 

Create CSR (Certficate Sigining requet with public key genearted) and send it to any teusted CA (Go Daddy,Digicert)

CA signs using its CA's private key and CSR infomration recived by requester and shares digital certifcate back. So website ownner adds this cerficate in webserver

Whenever user of website access the site , it downloads the certficate whcih has CA signing information and by default many browerser trust pouplar CA (Go Daddy, Digiect etc) , if its in trusted certs trust is establied

# What is chaining - Root ,intermidiate and leaf

Lets say there are many internal users of website and with in same org mutiple websites having differnet CA certs , then instead of having all CA certs in trust store of internal user we can fallow chaining 

Create root cert whcih is self signed cert - generate public and private key and sign by itself (instead of creating CSR and sending to CA)

if leaf cert (cert got from CA) chained with root cert , then just by adding root cert all leaf certs chained with root cert will be accessed without adding them to user trust store



