# 08 – Database Schema

## Users

| Field           | Type    | Description                         |
|----------------|---------|-------------------------------------|
| user_id         | int PK  | Unique ID                           |
| ln_pubkey       | string  | Lightning pubkey (LNURL-auth)       |
| username        | string  | Optional nickname                   |
| joined_at       | datetime| First login timestamp               |

## Wishes

| Field             | Type     | Description                          |
|------------------|----------|--------------------------------------|
| wish_id           | int PK   | Unique wish ID                       |
| user_id           | FK       | Linked to Users                      |
| title             | string   | Short wish title                     |
| description       | text     | Longer wish explanation              |
| amount_target_usd | decimal  | USD value at time of post            |
| amount_target_sats| int      | Funding target in sats               |
| amount_raised_sats| int      | Accumulated sats                     |
| posted_at         | datetime | When posted                          |
| expires_at        | datetime | Auto-expiry timestamp                |
| fulfilled_at      | datetime | When (if) fulfilled                  |
| is_fulfilled      | boolean  | Fulfillment flag                     |
| is_expired        | boolean  | Expiration flag                      |

## Grants

| Field         | Type     | Description                          |
|--------------|----------|--------------------------------------|
| grant_id      | int PK   | Unique grant ID                      |
| wish_id       | FK       | Linked to wish                       |
| grantor_user_id | FK     | Who granted it                       |
| amount_sats   | int      | Amount given                         |
| granted_at    | datetime | Time of payment                      |
| is_full       | boolean  | Whether this fulfilled the wish      |

## Votes

| Field         | Type     | Description                          |
|--------------|----------|--------------------------------------|
| vote_id       | int PK   | Unique vote ID                       |
| wish_id       | FK       | Linked to wish                       |
| voter_user_id | FK       | Who voted                            |
| vote_type     | enum     | up or down                           |
| voted_at      | datetime | Time of vote                         |
