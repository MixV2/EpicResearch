# SetCosmeticLockerSlots

Similar to [SetCosmeticLockerSlot](https://github.com/MixV2/EpicResearch/blob/master/docs/mcp/profile/operations/SetCosmeticLockerSlot.md), but edits different slots of the Battle Royale locker at the same time.

## Attributes

Compatible Profiles: `athena`, `campaign`  
Supported MCPs: `fortnite`

## Payload

```json
{
  "lockerItem": "",
  "loadoutData": []
}
```

## Parameters
- `lockerItem`: GUID of item in inventory (e.g. `2099ae21-e941-44b6-aecd-bcf67abd442a`)
- `loadoutData`: Category's slotIndex to modify, it's a list of:
```json
    {
        "category": "",
        "itemToSlot": "",
        "slotIndex": 0,
        "variantUpdates": [],
    }
```

## loadoutData
  - `category`: type of item
    - Character
    - Dance
    - Glider
    - Pickaxe
    - Hat
    - Backpack
    - LoadingScreen
    - BattleBus
    - VehicleDecoration
    - CallingCard
    - MapMarker
    - ConsumableEmote
    - VictoryPose
    - SkyDiveContrail
    - MusicPack
    - ItemWrap
    - PetSkin
    - Charm
- `itemToSlot`: the internal ID of the item (e.g. `AthenaCharacter:cid_242_athena_commando_f_bullseye`)
- `slotIndex`: location of where the item should be placed in the loadout
- `variantUpdates`: selected variants for the item
  - If the item has multiple styles, then you will need to specify which style has been equipped - for example:
    ```json
    {
        "channel": "Material",
        "active": "Mat1",
        "owned": []
    }
    ```
