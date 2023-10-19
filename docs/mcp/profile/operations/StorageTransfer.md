# StorageTransfer
Transfers an item from/to storage.

## Attributes
Compatible Profiles: `theater0`  
Supported MCPs: `fortnite`

## Payload
```json
{
    "transferOperations": [
        "itemId": "",
	"quantity": 0,
	"toStorage": true,
	"newItemIdHint": ""
    ]
}
```

## Parameters
- `itemId`: ID of the item to transfer
- `quantity`: quantity of items to transfer
- `toStorage`: Boolean - true/false
- `newItemIdHint` - unknown
