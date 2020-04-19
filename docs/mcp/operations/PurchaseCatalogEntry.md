# PurchaseCatalogEntry
Purchases an item from the item shop.

## Attributes
Compatible Profiles: `athena`  
Supported MCPs: `fortnite`

## Payload
```json
{
    "offerId": "",
    "purchaseQuantity": 0,
    "currency": "MtxCurrency",
    "expectedTotalPrice": 0,
    "gameContext": ""
}
```

`offerId`: Offer ID of the item that is being purchased  
`purchaseQuantity`: Amount of item(s) being purchased  
`currency`: Type of currency the transaction is being paid in  
`expectedTotalPrice`: Price of the item  
`gameContext`: Only used for analytics and can be ignored  
