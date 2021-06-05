# SetCosmeticLockerSlot
Equip an item from the Battle Royale locker.

## Attributes
Compatible Profiles: `athena`  
Supported MCPs: `fortnite`

## Payload
```json
{
    "lockerItem": "",
    "category": "",
    "itemToSlot": "",
    "slotIndex": 0,
    "variantUpdates": [],
    "optLockerUseCountOverride": -1
}
```

## Parameters
- `lockerItem`: GUID of item in inventory (e.g. `2099ae21-e941-44b6-aecd-bcf67abd442a`)
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
- `slotIndex`: location of where the item should be placed in the loadout. If you would like to apply all item wraps at once you'll have to set this to -1
- `variantUpdates`: selected variants for the item
  - If the item has multiple styles, then you will need to specify which style has been equipped - for example:
    ```json
    {
        "channel": "Material",
        "active": "Mat1",
        "owned": []
    }
    ```
- `optLockerUseCountOverride`: Not sure what this means but keep it at either 0 or -1
