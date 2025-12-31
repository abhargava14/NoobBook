# Development Environment Setup Checklist

## ✅ Setup Complete!

All components have been successfully installed:

- ✅ **Python 3.11.14** (in backend/venv)
- ✅ **Node.js v22.17.1** (`/usr/local/bin/node`)
- ✅ **npm 10.9.2** (`/usr/local/bin/npm`)
- ✅ **Backend virtual environment** created and dependencies installed
- ✅ **Frontend node_modules** installed
- ✅ **.env file** created at `backend/.env`
- ✅ **ffmpeg** installed
- ✅ **LibreOffice** installed (as macOS app)
- ✅ **Playwright** browsers installed

## ⚠️ Next Steps

### 1. Configure API Keys

Edit `backend/.env` and add your API keys:

**Required API Keys:**
```bash
ANTHROPIC_API_KEY=sk-ant-...     # Get from https://console.anthropic.com
OPENAI_API_KEY=sk-...             # Get from https://platform.openai.com
PINECONE_API_KEY=...             # Get from https://app.pinecone.io
PINECONE_INDEX_NAME=...          # Your Pinecone index name
```

**Optional API Keys:**
```bash
ELEVENLABS_API_KEY=...          # Audio features
TAVILY_API_KEY=...              # Web search fallback
GOOGLE_CLIENT_ID=...            # Google Drive import
GOOGLE_CLIENT_SECRET=...
ANTHROPIC_TIER=1                # 1-4, controls rate limits
```

### 2. Start the Development Environment

Once API keys are configured, start both services:

```bash
python3 start.py
```

This will start:
- **Backend:** http://localhost:5000
- **Frontend:** http://localhost:5173

## Verification

After adding API keys, verify everything works:

1. **Backend:** Should start on http://localhost:5000
2. **Frontend:** Should start on http://localhost:5173
3. **Check logs:** Both services should show startup messages without errors

## Notes

- The `.env` file can also be configured via the Dashboard -> Settings UI after starting the app
- Some features may not work without optional API keys (audio, web search, Google Drive)
- The app will create necessary data directories automatically on first run
- LibreOffice is installed as a macOS application - the `soffice` command should be available via `/opt/homebrew/bin/soffice`

Create `backend/.env` with the following:

**Required API Keys:**
```bash
ANTHROPIC_API_KEY=sk-ant-...
OPENAI_API_KEY=sk-...
PINECONE_API_KEY=...
PINECONE_INDEX_NAME=...
```

**Optional API Keys:**
```bash
ELEVENLABS_API_KEY=...          # Audio features
TAVILY_API_KEY=...              # Web search fallback
GOOGLE_CLIENT_ID=...            # Google Drive import
GOOGLE_CLIENT_SECRET=...
ANTHROPIC_TIER=1                # 1-4, controls rate limits
```

### 4. System Dependencies
**Status:** ❌ Missing system packages

**macOS (using Homebrew):**
```bash
brew install libreoffice ffmpeg
npx playwright install
```

**Ubuntu/Debian:**
```bash
sudo apt install libreoffice ffmpeg
npx playwright install
```

## Quick Setup Commands

Run these commands in order:

```bash
# 1. Install system dependencies (macOS)
brew install libreoffice ffmpeg
npx playwright install

# 2. Setup backend
cd backend
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# 3. Setup frontend
cd ../frontend
npm install

# 4. Create .env file
cd ../backend
touch .env
# Then edit .env and add your API keys (see above)

# 5. Start the dev environment
cd ..
python3 start.py
```

## Verification Steps

After setup, verify everything works:

1. **Backend:** Should start on http://localhost:5000
2. **Frontend:** Should start on http://localhost:5173
3. **Check logs:** Both services should show startup messages without errors

## Notes

- The `.env` file can also be configured via the Dashboard -> Settings UI after starting the app
- Some features may not work without optional API keys (audio, web search, Google Drive)
- The app will create necessary data directories automatically on first run

