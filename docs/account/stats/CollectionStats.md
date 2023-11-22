## User Collection Stats (BULK)

## Request
| URL | Method | Auth Required |
| - | - | - |
| https://statsproxy-public-service-live.ol.epicgames.com/statsproxy/api/statsv2/query | `POST` | Yes |

### Query

**category**: `collection_fish`, `collection_character`

## Body

```json
{
  "appId": "Fortnite",
  "startDate": 0,
  "endDate": 9223372036854775807,
  "owners": []
}
```

``startDate``: 0 (for alltime) or set for custom time-window

``endDate``: 9223372036854775807 (for alltime) or set for custom time-window

``owners``: array of account ids (to get the stats from)
