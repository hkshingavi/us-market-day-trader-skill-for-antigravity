# US Market Day Trader Skill — Antigravity Adaptation Rules

This plugin is an Antigravity adaptation of the open-source [day-trader-skill](https://github.com/Jakeschincariol/day-trader-skill) originally created by Jake Schincariol.

The 11 modular skills, Python tooling, and sample configurations are structured for seamless operation inside the Google Antigravity environment.

## Guidelines for Antigravity Agents

- **Skill Execution:** Each skill provides a Python tool located in that skill's directory (`${SKILL_DIR}`). When executing commands, resolve `${SKILL_DIR}` to the actual directory of the active skill.
- **Safety First:**
  - Default to paper trading (`"paper": true`).
  - No orders may be executed without explicit user consent.
  - The risk manager (`trader-risk`) must validate the trade before any broker execution.
- **Broker Integration:**
  - Broker actions can run via MCP (e.g. Alpaca MCP server configured in `~/.gemini/config/mcp_config.json`).
- **Prerequisites:**
  - Python 3.8+ on system PATH.
  - Standard library only — no third-party pip dependencies required.
  - Set the `SEC_USER_AGENT` environment variable (e.g. `"Your Name user@example.com"`) for SEC EDGAR queries (`trader-news`, `trader-analyst`, `trader-pelosi`).
