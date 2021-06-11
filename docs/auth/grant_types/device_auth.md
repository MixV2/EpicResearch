# Authenticating by Device Auth
This form of authentication is primarily used by mobile devices on games such as [Fortnite](https://fortnite.com) and [Battle Breakers](https://www.epicgames.com/battlebreakers/en-US/home).  

Unlike exchange codes, a device auth is a set of three values that are needed to generate an access token, those being:
- Account ID
- Device ID
- Secret

## Advantages
- Device auth only expires in result of a user action (e.g. changing password) and not naturally
- Most clients support this grant type

## Disadvantages
- Can only generate access tokens for the client that the device auth was issued to
- To generate a device auth, you must already be authenticated

## Method
- Make sure you have an access token that is valid. If not, I suggest [getting one through an authorization code](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/authorization_code.md) and using the `fortniteIOSGameClient` client

- Send a `POST` request to https://account-public-service-prod.ol.epicgames.com/account/api/public/account/:accountId/deviceAuth (replacing `:accountId` with your own):  
  Required headers:
  - `Authorization`: Bearer (your access token)

  Make sure to save the response somewhere!

- Send a `POST` request to https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token:    
  Required headers:
  - `Content-Type`: application/x-www-form-urlencoded
  - `Authorization`: basic `clientId:secret` (encoded in Base64, must be the same client that was used to generate device auth)    
  
  Body:
  - `grant_type`: device_auth
  - `account_id`: (account id from before)
  - `device_id`: (device id from before)
  - `secret`: (secret from before)
  
If done successfully, you should now have a set of device auth credentials that can be used to authenticate at any time as well as an access token that can be used to access the rest of Epic's services!
