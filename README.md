# SSL-Playground

Create self signed signature in SF and download crt file
 
openssl x509 -pubkey -noout -in SelfSignedCert_06Dec2023_080740.crt > jwt_public.pem
 
# https://github.com/dannycoates/pem-jwk
npm install -g pem-jwk
 
kid="payments"
cat jwt_public.pem | pem-jwk | jq "{\"kid\": \"${kid}\", \"alg\": \"RS256\", \"use\": \"sig\"} + ."
 
