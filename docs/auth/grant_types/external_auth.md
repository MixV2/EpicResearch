# Authenticating with External Auth
A way of exchanging an external auth token (such as PSN, XBOX) for an Epic Games access token
Not very useful as of now due to not having the PSN/XBOX/Switch Fortnite clients

## Method
- Send a `POST` request to https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token:    
  Required headers:
  - `Content-Type`: application/x-www-form-urlencoded
  - `Authorization`: basic `clientId:secret` (encoded in Base64, [list of clients here](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/auth_clients.md))    
  
  Body:
  - `grant_type`: external_auth
  - `external_auth_type`: ...
  - `external_auth_token`: ...
  
## Parameters
- `external_auth_type`: an external auth type
  - psn
  - nintendo
  - xbl
  - google
  - facebook
- `external_auth_token`: external auth token, probably issued by PSN/XBL/whatever service provider (not too sure)
