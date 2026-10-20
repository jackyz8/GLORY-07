# FFGlory — patched deployment bundle

## Railway deployment
1. Upload/push the contents of this folder to a private GitHub repository.
2. Create a Railway project from that repository.
3. Set the environment variables shown in `.env.example` in Railway Variables. Use unique secrets; do not commit `.env`.
4. Build command: `pip install -r requirements.txt` (Railway normally detects Python requirements automatically).
5. Start command: `python app.py`.
6. Open the generated Railway domain and check `/health` for `status: ok`.

The included account/token JSON files are intentionally empty templates because the original archive contained authentication/session material. Add your own valid data privately at runtime. Do not upload secrets to GitHub.

## Important
- `CguFF_pb2.py`, `DRIFT/step1_clan.png`, `DRIFT/step2_clan.png`, and `DRIFT/favicon.ico` were not present in the source archive. Missing optional assets are listed in `MISSING_FILES.txt`; no fake protobuf modules were generated.
- `/api/guildinfo` now accepts an authenticated session or `X-Guild-API-Key` matching `GUILD_API_KEY`.
- `/api/clanjoin` is admin-only.
- `/health` reports service status and uptime.
- Initial admin creation is disabled unless `ADMIN_USERNAME` and `ADMIN_PASSWORD` are set.
- Static HTML deployment on Vercel alone will not run this Python backend; use a Python-capable host such as Railway for the full app.

## Local run
`pip install -r requirements.txt` then `python app.py`.
