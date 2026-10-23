# RIVA — Returns Integrity Virtual Analyst

Streamlit demo application for returns/refund investigation workflows. This is a prototype with illustrative rule-based scoring; it is not a validated fraud model and must not be used as the sole basis for customer decisions.

## Run locally

```bash
python -m pip install -r requirements.txt
python -m streamlit run app.py
```

For Gemini features, create `.streamlit/secrets.toml` locally with:

```toml
GEMINI_API_KEY = "your-api-key"
```

Never commit `secrets.toml`, API keys, or the local SQLite database to Git.

## Deploy with GitHub and Streamlit Community Cloud

1. Create a new GitHub repository and push `app.py`, `requirements.txt`, `.gitignore`, and this README.
2. In Streamlit Community Cloud, create an app from that repository, choose branch `main` and main file `app.py`.
3. In the app's Settings → Secrets, add:

```toml
GEMINI_API_KEY = "your-api-key"
```

4. Deploy/reboot the app.

## Important data note

The app uses a local SQLite database. On hosted platforms, local filesystem storage may not be durable across rebuilds/redeploys and is not a shared database for multiple users. Back up demo data and use a managed persistent database before production or multi-user use.
