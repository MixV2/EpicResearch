# Add Friend by Account ID
Send a friend request from Account ID.

If you want to get the Account ID from Display Name then follow [this](https://github.com/MixV2/EpicResearch/blob/master/docs/account/endpoints/get_account_by_display_name.md)

## Request
| URL | Method |
| - | - |
| https://friends-public-service-prod.ol.epicgames.com/friends/api/v1/{accountId}/friends/{FriendID} | `POST` |

## Parameters
- `accountId`: Account you are adding the friend from duh.
- `FriendID`: Account you are adding.