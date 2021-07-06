# PurchaseCatalogEntry
Purchases an item from the item shop.

## Attributes
Compatible Profiles: `common_core`  
Supported MCPs: `fortnite`, `wex`

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

## Parameters
- `offerId`: offer ID of the item that is being purchased  
- `purchaseQuantity`: amount of item(s) being purchased  
- `currency`: type of currency the transaction is being paid in  
- `expectedTotalPrice`: price of the item  
- `gameContext`: only used for analytics and can be ignored  
