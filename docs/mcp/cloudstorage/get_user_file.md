# Get User File
Returns a file stored in a user's cloudstorage.

## Request
| URL | Method |
| - | - |
| /:namespace/api/cloudstorage/user/:accountId/:uniqueFilename | `GET` |

## Parameters
- `accountId` - account ID of the current authenticated user
- `uniqueFilename` - unique name of the file to access