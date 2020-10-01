# Get Events
Gets the currently available events. Requires a valid access token.

## Request
| URL | Method |
| - | - |
| https://events-public-service-live.ol.epicgames.com/api/v1/events/{game}/download/{accountId} | `GET` |

## Parameters
- `game`: target game, eg. Fortnite
- `accountId`: target account ID

## Query String
- `region`: event region, eg. EU
- `platform`: event platform, eg. Windows
- `teamAccountIds`: account IDs
