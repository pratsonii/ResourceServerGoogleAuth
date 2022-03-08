# ResourceServerGoogleAuth
Resource server which validates id_token(JWT)

# Google auth details
https://accounts.google.com/.well-known/openid-configuration

# Resource Server
https://docs.spring.io/spring-security-oauth2-boot/docs/2.2.x-SNAPSHOT/reference/html/boot-features-security-oauth2-resource-server.html

#Generate Google Auth token using Postman
- Create ClientId and secret add redirect URL : https://www.getpostman.com/oauth2/callback
- Go to postman > Authorization > Type = OAuth2.0
- Grant type = Authorization Code
- Callback URL = https://www.getpostman.com/oauth2/callback
- Auth URL = https://accounts.google.com/o/oauth2/auth
- Access Token URL = https://accounts.google.com/o/oauth2/token
- Scope = profile openid
- Client Authentication = Send as basic Auth Header

Above steps will generate two tokens : Access token and Id token

1) Access token can be verified by introspection-uri (2nd configuration in properties file).
2) Id token can be verified by JWK (1st configuration in properties file).

Either of above method can be used at a time.
