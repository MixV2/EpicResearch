# Authenticating by Exchange Code
An exchange code is a one-time code that can be used to generate an access token. The code expires after use or 5 minutes after generation.

Games on the PC such as [Fortnite](https://fortnite.com) and [Battle Breakers](https://www.epicgames.com/battlebreakers/en-US/home) use this to identify who is playing the game.

**Note: As of 30/05/20, Epic have removed the 'id/api/exchange' endpoint, meaning that it is not possible to get an exchange code through a browser anymore.**

## Advantages
- Most clients accept this grant type
- Does not reveal sensitive information such as email or password

## Disadvantages
- Difficult to get programmatically due to captcha
- Expires after 5 minutes
- Cannot get through browser

## Method
- Send a `GET` request to https://account-public-service-prod.ol.epicgames.com/account/api/oauth/exchange with a valid `Authorization` header
- Send a `POST` request to https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token:    
  Required headers:
  - `Content-Type`: application/x-www-form-urlencoded
  - `Authorization`: basic `clientId:secret` (encoded in Base64, [list of clients here](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/auth_clients.md))    
  
  Body:
  - `grant_type`: exchange_code
  - `exchange_code`: (the code from before)
  
If done successfully, you should now have an `access_token` that you can use to access everything Epic has to offer!
