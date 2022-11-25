# Redeem Code

## Request
| URL | Method | Auth Required |
| - | - | - |
| https://www.epicgames.com/fortnite/ajax/redemption/validate-redemption-code?redeem-code={redeemCode} | `POST` | Yes |

## Headers
```
cookie: EPIC_BEARER_TOKEN={token}
```

## Form Data
```
hostPageId=code-redeem&redeem-code={RedeemCode}
```

## Parameters
- `redeemCode`: Redeem code
- `token`: Access token
