# Using Endpoints
In order to use these endpoints, you must first be authenticated - you will need an access token.  
If you are looking for an easy way to authenticate, you can generate one by using the [authorization code](https://github.com/MixV2/EpicResearch/blob/master/docs/auth/grant_types/authorization_code.md) grant type.

## Sending Request
Using your access token, you will need to add this header to all https://account-public-service-prod.ol.epicgames.com requests:
- `Authorization`: `bearer (your access token)`
