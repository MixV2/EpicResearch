# User Stats

## Request
| URL | Method | Auth Required |
| - | - | - |
| https://statsproxy-public-service-live.ol.epicgames.com/statsproxy/api/statsv2/query | `POST` | Yes |

```json
{
  "appId": "Fortnite",
  "startDate": 0,
  "endDate": 9223372036854775807,
  "owners": ["accountId"],
  "stats": ["s22_social_bp_level"]
}
```

## Parameters
- `owners`: Array of every Account Id to query
- `accountId`: Array of every Stat to query
