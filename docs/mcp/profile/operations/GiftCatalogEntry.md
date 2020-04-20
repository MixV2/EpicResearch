# GiftCatalogEntry
Gifts an item from the item shop.

## Attributes
Compatible Profiles: `athena`  
Supported MCPs: `fortnite`, `wex`

## Payload
```json
{
    "offerId": "",
    "purchaseQuantity": 0,
    "currency": "MtxCurrency",
    "expectedTotalPrice": 0,
    "gameContext": "",
    "receiverAccountIds": [""],
    "giftWrapTemplateId": "",
    "personalMessage": ""
}
```

## Parameters
- `offerId`: offer ID of the item that is being purchased  
- `purchaseQuantity`: amount of item(s) being purchased  
- `currency`: type of currency the transaction is being paid in  
- `expectedTotalPrice`: price of the item  
- `gameContext`: only used for analytics and can be ignored  
- `receiverAccountIds`: array with the ids of the accounts that are being gifted
- `giftWrapTemplateId`: the wrap of the gift; can be:
    * `"GiftBox:gb_default"`
    * `"GiftBox:gb_giftwrap1"`
    * `"GiftBox:gb_giftwrap2"`
    * `"GiftBox:gb_giftwrap3"`
    * `"GiftBox:gb_giftwrap4"`
- `personalMessage`: the gift's message; you shouldn't use this at the moment because the gift messages are disabled in-game, so you can get banned
