# US Market Day Trader Skill for Antigravity

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A suite of **11 modular trading skills adapted specifically for Google Antigravity**. 

Scan thousands of charts, monitor real-time news & SEC filings, calculate entry/exit setups, replay historical simulation outcomes with Monte Carlo, and enforce strict automated risk management before putting capital at risk.

> **Credits & Acknowledgements:**  
> Adapted for Google Antigravity from the original [day-trader-skill](https://github.com/Jakeschincariol/day-trader-skill) for Claude Code created by [Jake Schincariol](https://opusjake.ai).

---

## ⚡ The 11 Skills

| Skill | Name | Description |
|---|---|---|
| `trader-scanner` | Chart Scanner | Scans thousands of US stocks for setups (Opening-Range Breakouts, bull flags, oversold bounces). |
| `trader-news` | News Monitor | Real-time Yahoo Finance headlines, SEC 8-K filings, and day movements. |
| `trader-entry` | Entry Timer | Watches bar-by-bar (1m/5m) to signal precise breakout entries. |
| `trader-exit` | Exit Planner | Automatically plans stop-loss, profit targets (1R/2R), and flat-by-close limits. |
| `trader-timemachine` | Time Machine | Replays 10,000 simulated sessions using historical 5m bars + past setup hit rates. |
| `trader-budget` | Budget Manager | Sizes positions strictly according to your account equity and max loss per trade. |
| `trader-risk` | Risk Manager | Rigorous rule validation (R:R, max loss, trading windows) before order creation. |
| `trader-broker` | Order Executor | Renders verified bracket tickets (supports Alpaca MCP / paper trading by default). |
| `trader-alerts` | Price Alerts | Tracks stops, targets, NYSE bell, and market close flat alerts. |
| `trader-analyst` | Earnings Analyst | Evaluates SEC EDGAR XBRL company facts (revenue, EPS, margins YoY). |
| `trader-pelosi` | Pelosi Tracker | Parses US House Periodic Transaction Reports (PTRs) upon public filing. |

---

## 📦 Installation in Google Antigravity

### Option 1: Install as an Antigravity Plugin

Clone or copy this repository into your Antigravity plugins directory:

```powershell
# Windows
git clone https://github.com/hkshingavi/us-market-day-trader-skill-for-antigravity.git "$env:USERPROFILE\.gemini\config\plugins\us-market-day-trader-skill"
```

```bash
# macOS / Linux
git clone https://github.com/hkshingavi/us-market-day-trader-skill-for-antigravity.git ~/.gemini/config/plugins/us-market-day-trader-skill
```

Once installed, the plugin will load automatically into Antigravity on your next turn.

---

## ⚙️ Prerequisites & Setup

1. **Python 3.8+** installed and available on PATH.
2. **Zero external pip dependencies** — all tools use the Python standard library with public, free endpoints.
3. **SEC EDGAR User-Agent (Required for SEC tools):**
   The SEC requires a custom user-agent header containing your name and email.
   - On Windows (PowerShell):
     ```powershell
     [System.Environment]::SetEnvironmentVariable("SEC_USER_AGENT", "Your Name your.email@example.com", "User")
     ```
   - On Linux / macOS:
     ```bash
     export SEC_USER_AGENT="Your Name your.email@example.com"
     ```
4. **Broker Execution (Optional):**
   - Integrates with the official [Alpaca MCP Server](https://github.com/alpacahq/alpaca-mcp-server).
   - Configure Alpaca in `~/.gemini/config/mcp_config.json`.
   - Defaults to **Paper Trading** for safety.

---

## 🛡️ Safety & Disclaimer

- **Not Financial Advice:** This toolkit is for research, simulation, and educational purposes. Day trading involves substantial financial risk.
- **Explicit Confirmation Required:** No automated trades are ever placed without the user explicitly confirming each individual order ticket in chat.
- **Paper Trading First:** All configurations default to paper trading mode.

---

## 📄 License

MIT License. See [LICENSE](LICENSE) for details.
