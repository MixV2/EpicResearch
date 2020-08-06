# Authenticating by Authorization Code
Please keep in mind that authenticating with authorization code only works on client that have a *redirect URL configured*.  
If you want to get an access token for a client that doesn't have a redirect URL configured, use this method with client `fortnitePCGameClient` and then use [exchange code authentication](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/grant_types/exchange_code.md) to get another access token for the new client.

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

## Example
Here's what the final HTTP request should look like when you have generated an authorization code - for this example, I am authenticating with `fortnitePCGameClient`:
```http
POST https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token HTTP/1.1
Content-Type: application/x-www-form-urlencoded
Authorization: basic ZWM2ODRiOGM2ODdmNDc5ZmFkZWEzY2IyYWQ4M2Y1YzY6ZTFmMzFjMjExZjI4NDEzMTg2MjYyZDM3YTEzZmM4NGQ=

grant_type=authorization_code&code=(code from before)
```
