# Installation (binary release)

## 1. Download

From [Releases](https://github.com/jacobdcook/linkedin-automator-app/releases), download `LinkedInAutomator-v*-your-platform.zip` and extract the folder anywhere you have write access (e.g. `Documents`).

## 2. Run the app

- **Windows:** double-click `LinkedInAutomator.exe` inside the extracted folder.  
- **Linux / macOS:** run the `LinkedInAutomator` executable (you may need `chmod +x LinkedInAutomator` on Linux).

## 3. First-time configuration

If the app starts without `config.json`, use **Run First-Time Setup** in the welcome prompt, or run the wizard from a machine that has Python and the source tree (`python3 setup_first_run.py`). The wizard asks for your name, resume text, LinkedIn About (optional), GitHub URL (optional), target roles, locations, and whether you use **Ollama** for local AI.

- If you **do not** use Ollama, the tool uses **template-only** mode until you add Ollama or a Groq key in Settings.

## 4. Playwright browser (required once)

Automation uses **Chromium** via Playwright. Browsers are **not** bundled in the zip (too large).

On a computer with **Python 3** and Playwright installed:

```bash
pip install playwright
python3 -m playwright install chromium
```

After this, the browser cache is shared for your user account; the frozen app can drive that browser when paths align. If the binary build cannot find Chromium, install via Python on the same machine and retry.

## 5. LinkedIn session

Log in once using the Hub **Dev Tools → Re-Login LinkedIn** flow or the documented `setup_session` script from source. Keep `session.json` in the app directory (or paths your build expects).

## 6. Simple vs Advanced

The Hub top bar has **Simple** and **Advanced**. Simple Mode shows four main actions; Advanced shows all tabs. Your choice is saved in `config.json` under `hub_ui.simple_mode`.

## License

BSL 1.1 — personal non-commercial use is free. See [LICENSE](LICENSE). Commercial use requires permission from the author.
