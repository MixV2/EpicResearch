# Get Accounts by ID
Similar to [getting an account by ID](https://github.com/MixV2/EpicResearch/blob/master/docs/account/endpoints/get_account_by_id.md), but intended for bulk account ID lookup. Supports up to 100 account IDs being looked up in one request.

## Request
| URL | Method |
| - | - |
| https://account-public-service-prod.ol.epicgames.com/account/api/public/account | `GET` |

## Query String
- `accountId`: target account ID(s) (can be repeated up to 100 times)
