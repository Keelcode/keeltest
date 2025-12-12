# KeelTest

AI-powered test generation for Python. Right in VS Code.

## What's this?

KeelTest is a VS Code extension that writes pytest unit tests for you. It analyzes your code, generates tests, runs them locally, and fixes failures automatically. You get working tests, not just code that looks good.

**The catch:** We guarantee 70%+ pass rate. If the tests don't pass, we refund your credits.

## Why not Copilot/Cursor/Claude?

Most AI coding assistants generate tests that look plausible but fail when you run them. They don't know your project structure, can't resolve imports correctly, and hallucinate mock configurations.

**KeelTest is different:**
- Runs tests locally before showing you results
- Fixes failures through iteration (reads error messages, adjusts code, retries)
- Analyzes your entire project for context (no import guessing)
- Only charges for tests that actually pass

Think of it as "Copilot with a QA loop" - you get verified, working code instead of plausible-looking suggestions.

## Install

Install from the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=KeelCode.keeltest) or search "KeelTest" in VS Code.

Get your API key at [keelcode.dev/account](https://keelcode.dev/account)

## Features

- Generates pytest tests per function
- Runs tests locally before showing you results
- Self-healing: automatically fixes failing tests through iteration
- Library-specific strategies (FastAPI, Pydantic, SQLAlchemy, pandas, etc.)
- Ruff formatting built-in
- Works with Poetry, UV or pip

## How it works

1. Right-click any Python file
2. Select "KeelTest: Generate Tests"  
3. Confirm the cost
4. Watch the progress panel
5. Get a test file with 70%+ pass rate guaranteed

Read the full docs in the extension's README or at [keelcode.dev/keeltest](https://keelcode.dev/keeltest)

## Pricing

Free tier: 7 credits/month  
1 credit = 1 small file (up to 15 functions)

Paid plans coming soon. [Join the waitlist](https://keelcode.dev/keeltest#pricing)

## Issues

Found a bug or have a feature request? [Open an issue](https://github.com/Keelcode/keeltest/issues)

## License

MIT - see extension/LICENSE

## Changelog

### 0.2.1
- Added support for UV
- Added "planner" agent
- Added "Fixtures Generator" agent
- Bug fixes

### 0.1.0
- Initial release
---

Made by [KeelCode](https://keelcode.dev)
