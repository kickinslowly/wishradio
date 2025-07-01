# 11 – Lightning Integration

## Wallet Model

- One **LNbits wallet per user**
- Each wish has an **LNURL-pay link** pointing to user’s wallet

## Authentication

- LNURL-auth using wallet signature
- Session tied to LN pubkey

## Grants

- On-demand invoices for each grant
- Avoids overfunding after fulfillment
- Grants tracked by webhook or polling

## Voting

- 5 sat invoice per vote
- Uses WebLN if available
- Otherwise shows QR code and prompts preload

## Admin Wallet

- All vote sats go to admin’s LNbits wallet
- Used for platform funding and stats
