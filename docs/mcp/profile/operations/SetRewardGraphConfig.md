# SetRewardGraphConfig
Update a reward graph config in an inventory.

## Attributes
Compatible Profiles: `athena`  
Supported MCPs: `fortnite`

## Payload
```json
{
    "state": [],
    "rewardGraphId": ""
}
```

## Parameters
- `state`: a list of node IDs (e.g. `ERG.Node.Tier01.0`)
- `rewardGraphId`: the GUID of the reward graph in inventory (e.g. `d0ee9d57-2109-4bb6-ae48-29332ebfd6f9`)
