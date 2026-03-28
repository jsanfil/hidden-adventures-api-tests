# Hidden Adventures API Tests

Local repo for Postman Native Git testing of the Hidden Adventures rebuild API.

## Intended Workflow

1. Open this repo in the Postman desktop app.
2. Click **Connect to workspace**.
3. Let Postman create and manage its Native Git structure:
   - `.postman/`
   - `postman/collections/`
   - `postman/environments/`
4. Build or sync the collection from inside Postman instead of importing standalone export JSON files.

## Why This Repo Is Minimal

The previous export-style Postman JSON files were removed on purpose.

For this repo, we want Postman to own the local workspace structure so it stays compatible with Native Git rather than behaving like an import-only folder.

## Local Assumptions

- server root: `http://127.0.0.1:3000`
- API base: `http://127.0.0.1:3000/api`
- Docker stack is already running from the server repo

## Suggested First Requests

- `GET /api/health`
- `GET /api/feed`
- `GET /api/adventures/:id`
- `GET /api/profiles/:handle`

## Current API Note

`viewerHandle` is still a temporary development-only stand-in for real authenticated viewer identity until Cognito-backed viewer resolution is wired.
