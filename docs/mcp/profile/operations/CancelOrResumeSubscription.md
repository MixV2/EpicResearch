# CancelOrResumeSubscription
Cancels/resumes a subscription (e.g. Fortnite Crew).

## Attributes
Compatible Profiles: `common_core`  
Supported MCPs: `fortnite`

## Payload
```json
{
	"appStore": "",
	"uniqueSubscriptionId": "",
	"willAutoRenew": false
}
```

## Parameters
- `appStore`: app store the subscription was created on
  - EpicPurchasingService
- `uniqueSubscriptionId`: ID of subscription to cancel/resume (found in profile)
- `willAutoRenew`: should the subscription renew automatically?
