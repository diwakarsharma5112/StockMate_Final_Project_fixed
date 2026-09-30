# StockMate - Inventory & Billing System

Flask inventory and billing project prepared for Render deployment.

## Render settings
- Runtime: Python 3
- Build Command: `pip install -r requirements.txt`
- Start Command: `gunicorn app:app`

The app uses SQLite for this demo version. On Render's free web service, the local filesystem is ephemeral, so database changes should not be treated as permanent. For permanent online inventory/sales data, migrate the database to PostgreSQL or use a persistent storage option.


## Recent fixes
- Product images are hidden from the Inventory and Billing screens while product image data remains compatible with the database.
- Bill generation now validates submitted products and quantities before writing anything to the database.
- Bill creation uses a database transaction and rolls back safely if a database error occurs.
- Selecting the same product multiple times is combined into one line to prevent inconsistent stock updates.
