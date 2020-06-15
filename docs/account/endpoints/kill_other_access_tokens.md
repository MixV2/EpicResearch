# Kill Other Access Tokens
Used for killing other access tokens other than your own current one. Useful if you have a bunch of inactive sessions and want to quickly terminate them.

## Request
| URL | Method |
| - | - |
| https://account-public-service-prod.ol.epicgames.com/account/api/oauth/sessions/kill | `DELETE` |

## Parameters
- `killType`: type of kill method
   - `ALL`
   - `OTHERS`
   - `ALL_ACCOUNT_CLIENT`
   - `OTHERS_ACCOUNT_CLIENT`
   - `OTHERS_ACCOUNT_CLIENT_SERVICE`