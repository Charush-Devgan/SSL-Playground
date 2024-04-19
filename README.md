# SSL-Playground

1. Create self signed signature using open ssl
 
2. openssl x509 -pubkey -noout -in {certificate file name}.crt > jwt_public.pem
3. npm install -g pem-jwk
4. kid="payments"
5. cat jwt_public.pem | pem-jwk | jq "{\"kid\": \"${kid}\", \"alg\": \"RS256\", \"use\": \"sig\"} + ."
 

references
https://github.com/dannycoates/pem-jwk
