# Authenticating by Token to Token
This grant type, `token_to_token`, can be used to generate an access token from an already existing access token.    

For example, if you had an access token (e.g. `abc123`), you could generate more access tokens (e.g. `def456` and `ghi789`) without invalidating the first token.

## Method
- Send a `POST` request to https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token:
  Required headers:
  - `Content-Type`: application/x-www-form-urlencoded  
  - `Authorization`: basic `clientId:secret` (encoded in Base64, [list of clients here](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/auth_clients.md))    
  
  Body:
  - `grant_type`: `token_to_token`  
  - `access_token`: (current access token)
