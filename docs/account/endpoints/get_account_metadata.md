# Get Account Metadata
This endpoint allows you to get the metadata of an account.  
In this case, metadata is only really used to get certain settings on account such as `LAUNCHER_SSO_OFF`.

## Request
| URL                                                                                             | Method |
| ----------------------------------------------------------------------------------------------- | ------ |
| https://account-public-service-prod03.ol.epicgames.com/account/api/accounts/:accountId/metadata | `GET`  |

## Parameters
- `accountId`: target account ID
