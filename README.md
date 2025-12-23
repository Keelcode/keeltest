# KeelTest

**Agentic Unit Test Generation for Python**

KeelTest is a VS Code extension that generates comprehensive `pytest` suites by verifying code execution in real-time. Unlike standard LLM assistants, it does not guess; it creates a plan, generates valid python code, executes it in a local sandbox, and iteratively fixes failures before presenting the final output.

[Website](https://keelcode.dev) | [Marketplace](https://marketplace.visualstudio.com/items?itemName=KeelCode.keeltest) | [Docs](https://keelcode.dev/keeltest)

## The Difference: Verification

Most AI tools treat test generation as a text completion task. KeelTest treats it as an engineering problem.

*   **Semantic Planning:** Analyzes your project structure and dependencies to build a test specification before writing code.
*   **The Triage Loop:** Executes generated tests in your local environment immediately.
*   **Auto-Correction:** If a test fails, the agent analyzes the traceback, distinguishes between hallucinations and source bugs, and attempts to fix the test code automatically.

## Requirements

*   **VS Code** ^1.80
*   **Python** ^3.8
*   **pytest** installed in your active environment
*   **Ruff** installed in your active environment for code formatting (optional, but recommended)
*   **pytest-asyncio** installed in your active environment if you have async code

## Quick Start

1.  **Install** the extension from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=KeelCode.keeltest).
2.  **Authenticate** with your API key from [keelcode.dev/account](https://keelcode.dev/account).
3.  **Right-click** any Python file and select **KeelTest: Generate Tests**.

## Supported Environments

The extension automatically detects and uses your project's dependency manager:
*   `uv`
*   `poetry`
*   `pip` / `venv`

## License

[MIT](LICENSE)
