# KeelTest

**Agentic Unit Test Generation for Python**

KeelTest is a VS Code extension that generates comprehensive `pytest` suites by verifying code execution in real-time. Unlike standard LLM assistants, it does not guess; it creates a plan, generates valid python code, executes it in a local sandbox, and iteratively fixes failures before presenting the final output.

<br/>
<img src="https://keelcode.dev/demo.gif" alt="KeelTest Demo" width="100%" />
<br/>

[Website](https://keelcode.dev) | [Marketplace](https://marketplace.visualstudio.com/items?itemName=KeelCode.keeltest) | [Docs](https://keelcode.dev/keeltest) | [Watch Full Demo](https://keelcode.dev/demo.mp4)

## The Difference: Verification

Most AI tools treat test generation as a text completion task. KeelTest treats it as an engineering problem.

* **Semantic Planning:** Analyzes your project structure and dependencies to build a test specification before writing code.
* **The Triage Loop:** Executes generated tests in your local environment immediately.
* **Auto-Correction:** If a test fails, the agent analyzes the traceback, distinguishes between hallucinations and source bugs, and attempts to fix the test code automatically.

For a deep dive into our architecture, read [How KeelTest Works](https://keelcode.dev/blog/introducing-keeltest).

## Requirements

* **VS Code** ^1.80
* **Python** ^3.8
* **pytest** installed in your active environment
* **Ruff** installed in your active environment for code formatting (optional, but recommended)
* **pytest-asyncio** installed in your active environment if you have async code

## Quick Start

1. **Install** the extension from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=KeelCode.keeltest).
2. **Authenticate** with your API key from [keelcode.dev/account](https://keelcode.dev/account).
3. **Right-click** any Python file and select **KeelTest: Generate Tests**.

## Supported Environments

The extension automatically detects and uses your project's dependency manager:

* `uv`
* `poetry`
* `pip` / `venv`

## Changelog

### 0.6.11 (2025-01-10)

**Better handling of missing dependencies**
* Now checks if your source file can be imported BEFORE starting test generation. If a dependency is missing (like Airflow providers, AWS SDKs, etc.), you'll get an immediate, clear error message instead of watching it retry 20+ times.

**Smarter class instantiation**
* When generating fixtures for classes with inheritance, KeelTest now passes the full constructor signature (including inherited parameters) to the AI. This fixes issues where tests failed because parent classes require specific constructor arguments passed via `**kwargs`.

**Planner insights reach the AI**
* Warnings detected during test planning (about inheritance patterns, required mocks, etc.) are now included directly in the generation prompt, so the AI can address them on the first try instead of discovering them through failed retries.

### 0.6.10 (2025-01-08)

**Improved Dependency Resolution & Context Gathering**
* Transitive dependency walking: Now resolves imports 2 levels deep with cycle detection
* Better type inference: Two-pass AST analysis resolves function return types in init assignments
* Parent class inheritance: Constructor params and class attributes collected from full inheritance chain
* Enhanced prompt context: Dependencies grouped by "DIRECT" vs "TRANSITIVE" for clearer LLM context

**Fixture Generation Improvements**
* `isinstance()` detection: AST analyzer now detects `isinstance()` checks in constructors and warns that MagicMock will fail these checks
* Constructor type check warnings: Prompts now display which params require real types vs MagicMock
* Fixture generator guidance: Added explicit examples showing correct fixture patterns

**Other fixes**
* Files with hyphens in their names now generate valid test imports using `importlib`
* Improved check for "untestable" files

## License

[MIT](LICENSE)
