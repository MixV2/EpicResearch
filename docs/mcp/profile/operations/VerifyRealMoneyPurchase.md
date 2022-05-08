# VerifyRealMoneyPurchase
Checks for profile changes after a real money purchase.

## Attributes
Compatible Profiles: `common_core`  
Supported MCPs: `fortnite`

## Payload
```json
{
	"appStore": "",
	"appStoreId": "",
	"receiptId": "",
	"receiptInfo": "",
	"purchaseCorrelationId": ""
}
```

## Parameters
- `appStore`: app store the purchase was made on
  - EpicPurchasingService
- `appStoreId`: offer's ID (can be found in the bulk offers response)
- `receiptId`: ID of the purchase receipt
- `receiptInfo`: info about the receipt
  - ENTITLEMENT
- `purchaseCorrelationId`: ID of the purchase correlation