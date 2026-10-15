# Design2Code

Upload a screenshot of a website design, describe what it should do, and Claude writes the full website code (HTML/CSS/JS) with live preview.

## Run it

```bash
pip install -r requirements.txt
export ANTHROPIC_API_KEY=sk-ant-...      # Windows PowerShell: $env:ANTHROPIC_API_KEY="sk-ant-..."
python app.py
```

Open http://127.0.0.1:5000

If you don't set `ANTHROPIC_API_KEY`, paste your key into the sidebar field instead (it is sent only to your own Flask server).

## How to use

1. Drop / paste one or more design screenshots (multiple images become sections/pages of one site).
2. Describe the functions (forms, buttons, filters, dark mode, etc.).
3. Click **Generate website**, then check **Preview** and **Code**.
4. Use the **Refine** box to ask for changes ("make the header sticky").
5. **Download** the code (single file, or a zip when using separate files).

## Files

- `app.py` : Flask backend; holds the prompt and streams Claude's output (key stays server-side)
- `index.html` : the web UI
- `requirements.txt` : `flask`, `anthropic`

## Notes

- Keep `app.py` bound to `127.0.0.1` for personal use. If you deploy it publicly, add authentication and rate limiting first, or anyone could spend your API credit.
- Quality depends on the screenshot: clear, full-width screenshots give the best results. Opus gives the most accurate output, Haiku is cheapest.
