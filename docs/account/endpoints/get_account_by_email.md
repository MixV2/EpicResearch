# Get Account by Email (Deprecated)
Get information about an account by Email lookup. Returns account ID, display name, links and external auths.  
Returns sensitive information if you are the owner of the account (like email address, full name, phone number, etc..).
* This method doesn't work anymore

## Request
| URL | Method |
| - | - |
| https://account-public-service-prod.ol.epicgames.com/account/api/public/account/email/{email} | `GET` |

## Parameters
- `email`: target account email
