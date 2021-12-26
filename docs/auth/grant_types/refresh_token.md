# Authenticating by Refresh Token
This grant type allows you to "refresh" an authentication session. It is used when an original authentication session expires and needs to be renewed.

## Method
- Send a `POST` request to https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token:  
  Required headers:
  - `Content-Type`: application/x-www-form-urlencoded  
  - `Authorization`: basic `clientId:secret` (encoded in Base64, [list of clients here](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/auth_clients.md))    
  
  Body:
  - `grant_type`: refresh_token
  - `refresh_token`: (`refresh_token` property from auth session)