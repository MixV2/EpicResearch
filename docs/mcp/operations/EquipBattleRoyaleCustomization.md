# EquipBattleRoyaleCustomization
Equip an item from the Battle Royale locker.

## Attributes
Compatiable Profiles: `athena`
Supported MCPs: `fortnite`

## Payload
```json
{
    "slotName": "",
    "itemToSlot": "",
    "indexWithinSlot": 0,
    "variantUpdates": []
}
```

## Parameters
- `slotName`: type of item
- `itemToSlot`: GUID of item in inventory (e.g. `2099ae21-e941-44b6-aecd-bcf67abd442a`)
- `indexWithinSlot`: location of where the item should be placed in the loadout
- `variantUpdates`: selected variants for the item

### Item Types
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
