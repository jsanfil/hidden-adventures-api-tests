# Hidden Adventures API Tests

Local repo for Postman Native Git testing of the Hidden Adventures rebuild API.

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

- `postman/collections/hidden-adventures-slice-1.collection.yaml`
- `postman/environments/hidden-adventures-local.environment.yaml`
- Postman-managed workspace metadata under `.postman/`

## Local Assumptions

- server root: `http://127.0.0.1:3000`
- API base: `http://127.0.0.1:3000/api`
- Docker stack is already running from the server repo

## Suggested First Requests

- `GET /api/health`
- `GET /api/feed`
- `GET /api/adventures/:id`
- `GET /api/profiles/:handle`

## Example Variables

The local environment includes a few concrete examples from the published migration dataset:

- `publicAdventureId`
- `connectionsAdventureId`
- `profileHandle`
- `connectedViewerHandle`

If you republish different data, update those values from Postman or edit the environment YAML directly.

## Current API Note

`viewerHandle` is still a temporary development-only stand-in for real authenticated viewer identity until Cognito-backed viewer resolution is wired.
