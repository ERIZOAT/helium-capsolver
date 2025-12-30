# 🤖 Helium + CapSolver: Unstoppable Python Web Automation

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
[![CapSolver](https://img.shields.io/badge/CAPTCHA%20Solver-CapSolver-green)](https://www.capsolver.com/?utm_source=github&utm_medium=repo&utm_campaign=helium-capsolver)

## 🌟 Project Overview

This repository provides a robust, easy-to-use framework for integrating **Helium** (a simplified Selenium wrapper) with **CapSolver** (an AI-powered CAPTCHA solving service).

The goal is to enable seamless, reliable web automation in Python, allowing your scripts to automatically handle modern CAPTCHA challenges like **Cloudflare Turnstile** and **reCAPTCHA** without manual intervention.

### Key Features

*   **Simplified Automation**: Leverage Helium's human-readable API (`click("Submit")`, `write("text", into="field")`).
*   **AI-Powered CAPTCHA Solving**: Integrate CapSolver's API for automatic resolution of complex challenges.
*   **Robust Examples**: Ready-to-run examples for reCAPTCHA v2, reCAPTCHA v3, and Cloudflare Turnstile.
*   **Anti-Detection Best Practices**: Includes configurations to make your automated browser appear more human.

## 🚀 Getting Started

### Prerequisites

*   Python 3.8+
*   A CapSolver API Key (Get yours [here](https://dashboard.capsolver.com/dashboard/overview/?utm_source=github&utm_medium=repo&utm_campaign=helium-capsolver))

### Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/helium-capsolver-solver.git
    cd helium-capsolver-solver
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Set your API Key:**
    For security, it is highly recommended to set your CapSolver API key as an environment variable.

    ```bash
    # Linux/macOS
    export CAPSOLVER_API_KEY="YOUR_API_KEY"

    # Windows (Command Prompt)
    set CAPSOLVER_API_KEY="YOUR_API_KEY"
    ```
    Alternatively, you can modify the `CAPSOLVER_API_KEY` variable directly in the example files.

## 💡 Usage Examples

All core examples are located in the `src/` directory.

### 1. Core CAPTCHA Solving Logic

The `core_solver.py` file contains the reusable functions for interacting with the CapSolver API: `create_task`, `get_task_result`, and `solve_captcha`.

```python
# src/core_solver.py (Snippet)
import time
import requests

CAPSOLVER_API = "https://api.capsolver.com"
CAPSOLVER_API_KEY = os.environ.get("CAPSOLVER_API_KEY", "YOUR_API_KEY") # Reads from environment

def solve_captcha(task_payload: dict) -> dict:
    """Complete CAPTCHA solving workflow."""
    # ... implementation ...
    pass
```

### 2. Solving reCAPTCHA v2

This example demonstrates solving a reCAPTCHA v2 challenge, including automatic site key detection and token injection using the underlying Selenium driver.

**Run the example:**
```bash
python src/recaptcha_v2_solver.py
```

### 3. Solving Cloudflare Turnstile

This script shows how to solve a Cloudflare Turnstile challenge and inject the resulting token into the required form field.

**Run the example:**
```bash
python src/turnstile_solver.py
```

### 4. Solving reCAPTCHA v3 (Score-Based)

For score-based CAPTCHAs, this example shows how to obtain a token with a specific action and minimum score.

**Run the example:**
```bash
python src/v3_solver.py
```

## ⚙️ Best Practices

To maximize the success rate of your automation:

1.  **Use Anti-Detection Flags**: Configure your Chrome options to disable automation flags (see `src/recaptcha_v2_solver.py` for an example).
2.  **Implement Random Delays**: Add random `time.sleep()` calls between actions to mimic human behavior.
3.  **Robust Error Handling**: Always use `try...except` blocks and implement retry logic for API calls (see `src/core_solver.py`).

## 🤝 Contributing

We welcome contributions! Please see our [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to submit pull requests, report bugs, and suggest features.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
*Disclaimer: This project is for educational and ethical automation purposes only. Please respect the terms of service of the websites you interact with.*
*P.S. Get bonus credits when you sign up for CapSolver using the code **`HELIUM`**!*
