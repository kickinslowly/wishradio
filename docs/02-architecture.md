# 02 – System Architecture

## High-Level Components

- **Frontend**: Web-based (Three.js + Cannon.js), interacts with API
- **Backend**: Python (Flask or FastAPI), handles auth, wishes, payments
- **Database**: SQLite (v1) → PostgreSQL (scaling)
- **Lightning Layer**: LNbits for wallets, LNURL-auth, on-demand invoices

## Architecture Diagram

```
User (browser)
  ↓
Three.js + Cannon.js UI
  ↓
Backend (Flask/FastAPI)
  ↙         ↘
SQLite     LNbits (Lightning)
```

## Communication

- RESTful API
- Polling for real-time updates
- LNbits webhooks or polling for payment confirmation
