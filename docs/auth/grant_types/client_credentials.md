
# Authenticating using client credentials
A client credentials session can be used to perform non-user actions such as obtaining cloudstorage, checking for updates, retrieving the catalog, checking [lightswitch](https://lightswitch-public-service-prod.ol.epicgames.com/lightswitch/api/service/fortnite/status), and many more.

## Method
- Choose the client you want to get an access token for from the [auth clients list](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/auth_clients.md)
- Send a `POST` request to https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token:    
  Required headers:
  - `Content-Type`: application/x-www-form-urlencoded
  - `Authorization`: basic `clientId:secret` (encoded in Base64, [list of clients here](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/auth_clients.md))    
  
  Body:
  - `grant_type`: client_credentials
  
If done successfully, you should now have an access token that you can use to access some Epic's services!
