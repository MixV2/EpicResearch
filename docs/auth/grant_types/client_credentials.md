
# Authenticating using client credentials

## Method
- Choose the client you want to get an access token for from the [auth clients list](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/auth_clients.md)
- Send a `POST` request to https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token:    
  Required headers:
  - `Content-Type`: application/x-www-form-urlencoded
  - `Authorization`: basic `clientId:secret` (encoded in Base64, [list of clients here](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/auth_clients.md))    
  
  Body:
  - `grant_type`: client_credentials
  
If done successfully, you should now have an access token that you can use to access some Epic's services! (e.g: Cloudstorage)
