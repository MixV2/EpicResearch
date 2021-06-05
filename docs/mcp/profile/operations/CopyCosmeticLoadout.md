# ClaimLoginReward
Copies or saves a cosmetic loadout.

## Attributes
Compatible Profiles: `athena`
Supported MCPs: `fortnite`

## Payload
```json
{
    "optNewNameForTarget": "",
    "sourceIndex": "",
    "targetIndex": ""
}
```

- `optNewNameForTarget`: Idk what this is (You can leave the string empty)
- `sourceIndex`: Index of the loadout you want to copy (e.g. 1). `targetIndex` has to be `0` if you want to copy a loadout.
- `targetIndex`: Index of the loadout you want to save (e.g. 1). `sourceIndex` has to be `0` if you want to save a loadout.

