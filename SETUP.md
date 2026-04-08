# Installation (binary release)

## 1. Download

From [Releases](https://github.com/jacobdcook/linkedin-automator-app/releases), download the zip for your platform. Current beta:

- **Linux x86_64:** `LinkedInAutomator-v0.1.0-beta-linux.zip`

Extract the folder anywhere you have write access (for example `Documents`).

## 2. Run the app

- **Windows:** double-click `LinkedInAutomator.exe` inside the extracted folder when a Windows build is available.  
- **Linux / macOS:** run the `LinkedInAutomator` executable (you may need `chmod +x LinkedInAutomator` on Linux).

## 3. First-time configuration

**Quick setup (in the Hub):** Use **Setup** in the top bar for Quick setup: add a **Groq** API key for cloud AI, paste **config JSON from Claude** using the prompt bundled with the app docs, and adjust basics without editing raw JSON.

If the app starts without `config.json`, use **Run First-Time Setup** in the welcome prompt, or run the wizard from a machine that has Python and the source tree (`python3 setup_first_run.py`). The wizard asks for your name, resume text, LinkedIn About (optional), GitHub URL (optional), target roles, locations, and whether you use **Ollama** for local AI.

- If you **do not** use Ollama or Groq, the tool uses **template-only** mode until you add Ollama or a Groq key in Settings or Quick setup.

## 4. Playwright browser (required once)

Automation uses **Chromium** via Playwright. Browsers are **not** bundled in the zip (too large).

**Running from a Python / source install:** On first launch, if Chromium is missing and Playwright is installed, the Hub runs `python3 -m playwright install chromium` in the background.

**Frozen Linux zip:** If Chromium is still missing, install once from a terminal on the same user account:

```bash
pip install playwright
python3 -m playwright install chromium
```

After this, the browser cache is shared for your user account. If automation cannot find Chromium, confirm Playwright’s cache under `~/.cache/ms-playwright` on Linux or set `PLAYWRIGHT_BROWSERS_PATH` if you use a custom location.

## 5. LinkedIn session

Log in once using the Hub **LinkedIn login** button (terminal flow), **Dev Tools → Re-Login LinkedIn**, or the documented `setup_session` script from source. Restart the Hub after refreshing the session if automation still fails.

## 6. Simple vs Advanced

The Hub top bar has **Simple** and **Advanced**. Simple Mode shows four main actions; Advanced shows all tabs. Your choice is saved in `config.json` under `hub_ui.simple_mode`.

## License

BSL 1.1 — personal non-commercial use is free. See [LICENSE](LICENSE). Commercial use requires permission from the author.
