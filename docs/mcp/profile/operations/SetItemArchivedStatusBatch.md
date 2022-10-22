# SetItemArchivedStatusBatch
Used to archive cosmetics owned by the user.

## Attributes
Compatible Profiles: `athena`  
Supported MCPs: `fortnite`

## Payload
```json
{
    "itemIds": [
        ""
    ],
    "archived": true
}
```

## Parameters
- `itemIds`: GUID of the cosmetic in question, grabbed from [QueryProfile](https://github.com/MixV2/EpicResearch/blob/master/docs/mcp/profile/operations/QueryProfile.md)
- `archived`: Boolean true archives false unarchives
