# 05 – Grants

## Purpose

Allows any logged-in user to contribute sats toward a wish (partial or full funding).

## Flow

1. User clicks “Grant Wish”
2. User chooses amount to contribute
3. Server generates Lightning invoice (on-demand)
4. User pays invoice
5. Webhook/poll confirms payment
6. Grant recorded in DB, wish updated

## Key Fields

- `grant_id`
- `wish_id`
- `grantor_user_id`
- `amount_sats`
- `granted_at`
- `is_full` (whether this fulfilled the wish)

## Notes

- Overfunding is allowed
- Each grant is recorded individually
