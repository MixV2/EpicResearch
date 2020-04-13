# Authenticating by Exchange Code
An exchange code is a one-time code that can be used to generate an access token. The code expires after use or 5 minutes after generation.

Games on the PC such as [Fortnite](https://fortnite.com) and [Battle Breakers](https://www.epicgames.com/battlebreakers/en-US/home) use this to identify who is playing the game.

## Advantages
- Very easy to get from a browser
- Most clients accept this grant type
- Does not reveal sensitive information such as email or password

## Disadvantages
- Difficult to get programmatically due to captcha
- Provides full access to an account

## Obtaining an Exchange Code
- Open https://www.epicgames.com/id/login?redirectUrl=https%3A%2F%2Fwww.epicgames.com%2Fid%2Fapi%2Fexchange in a browser
- Send a `POST` request to https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token:    
  Required headers:
  - `Content-Type`: application/x-www-form-urlencoded
  - `Authorization`: basic clientId:secret (encoded in Base64)    
  
  Body:
  - `grant_type`: exchange_code
  - `exchange_code`: (the code from before)
  
If done successfully, you should now have an `access_token` that you can use to access everything Epic has to offer!
