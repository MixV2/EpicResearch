# Upload User File
Uploads a file to be stored in the user's cloudstorage.

## Request
| URL | Method |
| - | - |
| /:namespace/api/cloudstorage/user/:accountId/:uniqueFilename | `PUT` |

## Payload
- binary data of file to upload

## Parameters
- `accountId` - account ID of the current authenticated user
- `uniqueFilename` - unique name of the file to access