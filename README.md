# Hidden Adventures API Tests

Postman collection and local environment for exercising the current Hidden Adventures rebuild API.

## Files

- `Hidden Adventures Local.postman_collection.json`
- `Hidden Adventures Local.postman_environment.json`

## Current API Coverage

- health check
- public feed
- feed with a connected viewer
- public adventure detail
- connections-only adventure detail
- public profile
- profile with a connected viewer

## Import Into Postman

1. Import `Hidden Adventures Local.postman_collection.json`.
2. Import `Hidden Adventures Local.postman_environment.json`.
3. Select the `Hidden Adventures Local` environment.

## Local Assumptions

- server root: `http://127.0.0.1:3000`
- API base: `http://127.0.0.1:3000/api`
- Docker stack is already running from the server repo

## Notes

- `viewerHandle` is a temporary development-only stand-in for real authenticated viewer identity.
- The collection includes one request that should return `404` for a connections-only adventure when no viewer is provided.
