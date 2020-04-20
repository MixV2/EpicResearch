# UnlockRewardNode
Unlocks a reward by a node ID. Used in [Winterfest 2019](https://www.epicgames.com/fortnite/en-US/news/winterfest-2019-begins?sessionInvalidated=true) to unlock presents in-game and is also used to unlock styles for [Gear Specialist Maya](https://fnbr.co/outfit/gear-specialist-maya).

## Attributes
Compatible Profiles: `athena`  
Supported MCPs: `fortnite`

## Payload
```json
{
    "nodeId": "",
    "rewardGraphId": "",
    "rewardCfg": ""
}
```

## Parameters
- `nodeId`: the ID of the node being unlocked
- `rewardGraphId`: the GUID of the reward graph in inventory (e.g. `d0ee9d57-2109-4bb6-ae48-29332ebfd6f9`)
- `rewardCfg`: unknown, can be set to empty for this
