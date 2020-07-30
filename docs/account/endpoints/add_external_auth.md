# Add External Auth
Adds an external auth to an account.  
Used for linking accounts with services such as XBOX, PSN, WeGame, etc..

## Request
| URL | Method |
| - | - |
| https://account-public-service-prod.ol.epicgames.com/account/api/public/account/{accountId}/externalAuths | `POST` |

## Payload
```json
{
    "authType": "",
    "externalAuthToken": ""
}
```

## Parameters
- `accountId`: target account ID
- `authType`: the authentication method used by the third party that is being linked (e.g. `wegame_rail_session_ticket`)
- `externalAuthToken`: the authentication token used by the third party to verify ownership