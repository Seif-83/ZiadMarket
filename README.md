# عطارة الأخوة

Small Vite/React project. This repository hosts the source for the site.

How to run locally:

```powershell
npm install
npm run dev
```

To deploy to GitHub Pages, enable the included GitHub Actions workflow.

Running the local AI proxy (optional, recommended):

1. Install server dependencies:

```powershell
cd server
npm init -y
npm install express cors body-parser @google/genai
```

2. Set your Google GenAI API key (keep this secret). In PowerShell:

```powershell
$env:GOOGLE_GENAI_API_KEY = "YOUR_KEY_HERE"
```

Or create a `.env` and export it in your shell. Then run:

```powershell
node server/server.js
```

3. Run the frontend:

```powershell
# in project root
npm run dev
```

Now opening a product modal will call `POST /api/benefits` on the proxy server which will query Google GenAI and return the benefits.

Security note: Do not embed secret API keys in client-side env vars for production. Use a backend/proxy (like the server above) or serverless function and keep keys in environment variables/secrets.
