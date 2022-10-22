# UpdateQuestClientObjectives
Update a quest objective.

## Attributes
Compatible Profiles: `athena`, `campaign`  
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
- `statName`: name of the quest objective to complete (e.g. `quest_s12_donut_w7_a_1`)
- `count`: objective completion count
- `timestampOffset`: offset of timestamp
