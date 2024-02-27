# SSL-Playground

1. Create self signed signature in SF and download crt file
 
2. openssl x509 -pubkey -noout -in SelfSignedCert_06Dec2023_080740.crt > jwt_public.pem
https://github.com/dannycoates/pem-jwk
3. npm install -g pem-jwk
4.  
kid="payments"
cat jwt_public.pem | pem-jwk | jq "{\"kid\": \"${kid}\", \"alg\": \"RS256\", \"use\": \"sig\"} + ."
 
