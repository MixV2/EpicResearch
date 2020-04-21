# RespecAlteration
Replaces a perk on a campaign item.

## Attributes
Compatible Profiles: `campaign`  
Supported MCPs: `fortnite`

## Payload
```json
{
    "targetItemId": "",
    "alterationSlot": "",
    "alterationId": ""
}
```

## Parameters
- `targetItemId`: Item ID of the item that you want one of its perks replaced.
- `alterationSlot`: Index of the perk within the `alterations` field inside the `attributes` object. Starts at 0.
- `alterationId`: Template ID of the perk to replace to.
