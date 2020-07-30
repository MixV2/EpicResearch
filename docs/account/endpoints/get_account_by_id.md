# Get Account by ID
Get information about an account by ID lookup. Returns account ID, display name, links and external auths.  
Returns sensitive information if you are the owner of the account (like email address, full name, phone number, etc..).

## Request
| URL | Method |
| - | - |
| https://account-public-service-prod.ol.epicgames.com/account/api/public/account/{accountId} | `GET` |

## Parameters
- `accountId`: target account ID