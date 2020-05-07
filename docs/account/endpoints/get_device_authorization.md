# Get Device Authorization
Generates a code that can be used to link an external account to your Epic Games account.  
Primarily used on consoles with Fortnite.

## Request
| URL                                                                                             | Method |
| ----------------------------------------------------------------------------------------------- | ------ |
| https://account-public-service-prod03.ol.epicgames.com/account/api/oauth/deviceAuthorization    | `POST` |

## Payload
```form
prompt=promptType
```

## Parameters
- `prompt`: a prompt type (e.g. `login`, `register`)
