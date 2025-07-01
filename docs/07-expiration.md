# 07 – Expiration

## Purpose

Wishes should not persist indefinitely. Each wish expires automatically after **7 days** if not fulfilled.

## Flow

1. On creation, `expires_at` is set to `posted_at + 7 days`
2. Background job or check on user action marks expired wishes
3. Expired wishes are removed from active view
4. Bubble "pops" in frontend
5. Partial grants are **not refunded**

## Fulfilled vs Expired

- A wish marked as `fulfilled` is removed immediately
- A wish marked as `expired` is kept for stats/history but not shown in main room

## User Impact

- Wishers keep partial funds even if their wish expires
- Grantors cannot reverse payments (Lightning is final)
