# 09 – API Endpoints

## Authentication

### `GET /auth/lnurl`
- Returns LNURL-auth challenge and encoded URL
- Used to generate QR for login

### `POST /auth/callback`
- Params: `k1`, `sig`, `key`
- Verifies LNURL-auth and creates session

## Wishes

### `POST /wish`
- Auth required
- Body: `title`, `description`, `amount_usd`
- Creates a new wish

### `GET /wishes`
- Returns list of active wishes

### `GET /wish/<id>`
- Returns full info for a specific wish

## Grants

### `POST /grant/<wish_id>`
- Auth required
- Body: `amount_sats`
- Returns Lightning invoice for grant

### `GET /grant/status/<invoice_id>`
- Polling endpoint to check grant payment

## Votes

### `POST /vote/<wish_id>`
- Auth required
- Body: `type` ("up" or "down")
- Returns invoice or triggers WebLN

### `GET /vote/status/<vote_id>`
- Polling to confirm vote payment
