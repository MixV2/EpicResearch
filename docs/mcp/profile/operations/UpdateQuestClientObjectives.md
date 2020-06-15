# UpdateQuestClientObjectives
Update a quest objective.

## Attributes
Compatible Profiles: `athena`  
Supported MCPs: `fortnite`

## Payload
```json
{
    "advance": [
        {
            "statName": "",
            "count": 1,
            "timestampOffset": 0
        }
    ]
}
```

## Parameters
- `statName`: name of quest to complete (e.g. `quest_s12_donut_w7_a_1`)
- `count`: amount of quests to complete
- `timestampOffset`: offset of timestamp
