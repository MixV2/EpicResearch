# Authenticating by Device Code

## Method
- Make sure you have an access token that is valid. If not, I suggest getting one through the client credentials grant and using the `fortnitePCGameClient` client

- Get the `device_code` from sending a [get device authorization](https://github.com/MixV2/EpicResearch/blob/master/docs/account/endpoints/get_device_authorization.md) and then open the `verification_uri_complete` URL in a browser and login to your account

- Using the `device_code` from before, you can send a `POST` request to https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token:  
  Required headers:
  - `Content-Type`: application/x-www-form-urlencoded
  - `Authorization`: basic `clientId:secret` (encoded in Base64, [list of clients here](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/auth_clients.md))    
  
  Body:
  - `grant_type`: device_code
  - `device_code`: (the `device_code` from before)
  
  If done successfully, you should now have an active authentication session for the account that used the https://epicgames.com/id/activate link.
