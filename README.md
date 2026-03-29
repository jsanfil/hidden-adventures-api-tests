# Hidden Adventures API Tests

Local repo for Postman Native Git testing of the Hidden Adventures rebuild API.

## Role In The Program

- this repo is for manual API exploration and troubleshooting
- it should stay current with server contract changes
- it is not the official server test suite or acceptance runner
- the official server verification path is the Vitest suite in `hidden-adventures-server`

## Intended Workflow

1. Open this repo in the Postman desktop app.
2. Click **Connect to workspace**.
3. Let Postman create and manage its Native Git structure:
   - `.postman/`
   - `postman/collections/`
   - `postman/environments/`
4. Use the checked-in Local View resources under `postman/`.
5. Let Postman sync edits back into this repo instead of importing standalone export JSON files.

## What Is Checked In

- authenticated and unauthenticated Slice 1 request definitions under `postman/collections/hidden-adventures-slice-1/`
- `postman/environments/Hidden Adventures Local.environment.yaml`
- Postman-managed workspace metadata under `.postman/`

## Local Assumptions

- server root: `http://127.0.0.1:3000`
- API base: `http://127.0.0.1:3000/api`
- Docker stack is already running from the server repo
- authenticated requests use a real bearer token, not `viewerHandle`

## Suggested First Requests

- `GET /api/health`
- `GET /api/auth/bootstrap`
- `GET /api/feed`
- `GET /api/adventures/:id`
- `GET /api/profiles/:handle`

## Example Variables

The local environment includes a few concrete examples from the published migration dataset:

- `publicAdventureId`
- `connectionsAdventureId`
- `profileHandle`
- `authToken`
- `desiredHandle`

If you republish different data, update those values from Postman or edit the environment YAML directly.

## Current API Note

Connected-viewer behavior now comes only from authenticated auth context. Any request definition that models a viewer should use an `Authorization: Bearer {{authToken}}` header and should not send `viewerHandle`.
