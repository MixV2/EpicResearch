# Authenticating by Authorization Code
Best method to authenticate quickly since exchange code has been deprecated.

## Method
- Choose the client you want to get an access token for from the [auth clients list](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/auth_clients.md)
- Open https://www.epicgames.com/id/api/redirect?clientId=:clientId&responseType=code in a browser (make sure you are logged in with epicgames.com), replacing `:clientId` with the chosen client ID
- Send a `POST` request to https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token:    
  Required headers:
  - `Content-Type`: application/x-www-form-urlencoded
  - `Authorization`: basic `clientId:secret` (encoded in Base64, [list of clients here](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/auth_clients.md))    
  
  Body:
  - `grant_type`: authorization_code
  - `code`: (the code from the query string of the redirect response)
  
If done successfully, you should now have an access token that you can use to access Epic's services!
