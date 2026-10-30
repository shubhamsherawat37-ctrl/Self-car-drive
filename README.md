# AURORA DRIVE — Premium Car Rental Hackathon Project

A polished, responsive car-rental web app built with **Python + Flask + SQLite**, HTML, CSS and JavaScript.

## Features
- Premium, responsive landing page and vehicle collection
- Search form for pick-up location and dates
- Fleet filters and price sorting
- Reservation form with date validation and live price estimate
- Flask backend that saves bookings in SQLite
- Booking conflict prevention for overlapping date ranges
- Booking confirmation with unique reference code
- Rule-based “Aurora Concierge” that recommends vehicles by trip style
- Demo admin summary endpoint for booking count and revenue
- Six seeded example vehicles

## Run locally
Use Python 3.10+.

```bash
# 1. Open this project folder in VS Code
# 2. Create and activate a virtual environment (recommended)
python -m venv .venv

# Windows PowerShell:
.venv\Scripts\Activate.ps1

# Windows CMD:
.venv\Scripts\activate.bat

# macOS/Linux:
source .venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Start the app
python app.py
```

Open **http://127.0.0.1:5000** in your browser. The SQLite database `aurora_drive.db` is created automatically on first run.

## API routes
- `GET /api/cars` — list active vehicles
- `POST /api/bookings` — create a reservation; checks dates and booking conflicts
- `POST /api/concierge` — rule-based vehicle recommendations
- `GET /api/admin/summary` — demo booking/revenue summary

## Example booking request
```json
{
  "car_id": 1,
  "customer_name": "Demo User",
  "email": "demo@example.com",
  "phone": "+91 9876543210",
  "pickup_location": "New Delhi",
  "pickup_date": "2027-01-10",
  "return_date": "2027-01-12"
}
```

## Important before a public launch
This is a hackathon-ready prototype, not a production rental platform. Before public deployment, add user authentication, admin authorization, CSRF/rate limiting, stronger phone validation, secure secrets/configuration, a payment gateway, insurance/licence verification workflow, email/SMS notifications, tests, logging, and a real AI service if desired. The admin summary endpoint is intentionally unauthenticated for a local demo and must be protected before deployment. Prices and vehicle images are illustrative; verify licensing/usage rights and replace them with your actual fleet data.
