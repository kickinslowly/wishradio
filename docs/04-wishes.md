# 04 – Wishes

## What is a Wish?

A wish is a user-generated request for a specific item or amount of money (in USD/BTC), with an accompanying reason.

## Key Fields

- `wish_id`
- `user_id`
- `title`, `description`
- `amount_target_usd`, `amount_target_sats`
- `amount_raised_sats`
- `status`: open | fulfilled | expired
- `posted_at`, `expires_at`, `fulfilled_at`

## Flow

1. User submits wish via form
2. System converts USD to sats
3. LNURL-pay link created (points to user’s wallet)
4. Bubble appears in 3D space
