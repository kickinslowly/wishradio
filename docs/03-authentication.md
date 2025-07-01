# 03 – Authentication (LNURL-auth)

## Purpose

Users authenticate using their Lightning wallets via LNURL-auth, a secure passwordless method that identifies users by their public key derived for our domain.

## Flow

1. User clicks “Log in with Lightning”
2. Server generates a `k1` challenge and LNURL-auth QR
3. User’s wallet signs the challenge and calls back with their pubkey and signature
4. Server verifies signature and logs in the user
5. Session created and linked to user’s LN pubkey

## Storage

- User identified by LN pubkey (per-domain identity)
- No email, no password
- Optional nickname or alias stored in DB
