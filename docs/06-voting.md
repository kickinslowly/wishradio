# 06 – Voting

## Purpose

Allows users to express support or skepticism about a wish using paid upvotes or downvotes.

## Mechanics

- Each vote costs **5 sats**
- One vote per user per wish (up or down)
- Voting is **anonymous**
- Vote revenue goes to **admin wallet**

## Flow

1. User clicks upvote/downvote
2. If logged in:
   - Check for WebLN
   - If WebLN available: send 5 sats directly
   - If not: show QR invoice and prompt user to preload 100 sats (optional)
3. On payment success:
   - Record vote in DB
   - Update wish score
   - Bubble size and position adjusted accordingly

## Key Fields

- `vote_id`
- `wish_id`
- `voter_user_id`
- `vote_type`: up | down
- `voted_at`
