# Get Lightswitch Bulk Status
Gets the current lightswitch status for multiple apps.  
Determines whether these apps can or cannot be played at the time as well as giving catalog information related to the app(s).

## Request
| URL | Method |
| - | - |
| http://lightswitch-public-service-prod.ol.epicgames.com/lightswitch/api/service/bulk/status | `GET` |

## Parameters
- `serviceId`: multiple service IDs to check (e.g. Fortnite, WorldExplorersLive)