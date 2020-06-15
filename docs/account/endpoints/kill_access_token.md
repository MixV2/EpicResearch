# Kill Access Token
Kills an active access token.  

Good practice to call this endpoint whenever you are done with your token because if you have too many auth sessions active you will not be able to authenticate for a few hours.

## Request
| URL | Method |
| - | - |
| https://account-public-service-prod.ol.epicgames.com/account/api/oauth/sessions/kill/{accessToken} | `DELETE` |

## Parameters
- `accessToken`: access token to kill