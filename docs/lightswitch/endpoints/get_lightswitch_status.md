# Get Lightswitch Status
Gets the current lightswitch status for one app.  
Determines whether an app can or cannot be played at the time as well as giving catalog information related to the app.

## Request
| URL | Method |
| - | - |
| http://lightswitch-public-service-prod.ol.epicgames.com/lightswitch/api/service/:serviceId/status | `GET` |

## Parameters
- `serviceId`: service ID to check (e.g. Fortnite)