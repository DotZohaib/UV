# Hello Agent Project

A simple AI agent project using Python, environment variables, and the OpenAI API. This project also uses [**uv**](https://github.com/astral-sh/uv) — a next-generation Python package manager that is **faster** and **more reliable** than pip.

---

## 📦 What is `uv`?

`uv` is a modern Python package manager built for **speed**, **determinism**, and **developer experience**. It's a great alternative to `pip` and `pip-tools`.

### ✅ Why use `uv`?

- Blazing-fast dependency resolution and installation
- Compatible with `pip` and `requirements.txt`
- Replaces `pip`, `pip-tools`, and `virtualenv`
- Written in Rust for high performance

> Install it using:  
> ```bash
> pip install uv
> ```

---

## 🔧 Prerequisites

- Python 3.9+
- `uv` installed (`pip install uv`)

---

## 🚀 Project Setup

### 1. Create and initialize the project

```bash
uv init hello_agent
cd hello_agent
```

### 2. Add dependencies

```bash
uv add openai-agents python-dotenv
```

### 3. Create `.env` file

In the root directory, create a file named `.env` and add your OpenAI API key:

```env
OPENAI_API_KEY=your-api-key-here
```

### 4. Create `main.py`

```python
# main.py
import os
from dotenv import load_dotenv
from openai import OpenAI

# Load environment variables from .env file
load_dotenv()

# Initialize OpenAI client
client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))

# Your agent code
if __name__ == "__main__":
    print("Hello, AI Agent!")
```

### 5. Run the project

```bash
uv run main.py
```

---

## 📁 Project Structure

```
hello_agent/
├── .env
├── main.py
├── README.md
└── requirements.txt
```

---

## 🔐 Notes on Security

- Never commit your `.env` file to Git or version control.
- Add `.env` to your `.gitignore`:

```bash
echo ".env" >> .gitignore
```

---

## 🧪 Testing your Setup

Try running:

```bash
uv run main.py
```

If everything is set up correctly, you'll see:

```
Hello, AI Agent!
```

---

## 💡 Switching to Gemini API (Optional)

If you want to use Google's Gemini API instead of OpenAI:

1. Install `google-generativeai`:

```bash
uv add google-generativeai
```

2. In your `.env`, add:

```env
GEMINI_API_KEY=your-gemini-key-here
```

3. Use the appropriate Gemini client in your `main.py`.

---

## 📚 More about `uv`

Here are helpful resources to learn more about `uv`:

- GitHub: [https://github.com/astral-sh/uv](https://github.com/astral-sh/uv)
- Docs: [https://astral.sh/blog/uv](https://astral.sh/blog/uv)
- Speed comparison: [uv vs pip](https://github.com/astral-sh/uv#speed-comparison)

---

## ✅ Summary of `uv` Commands

| Command                  | Description                         |
|--------------------------|-------------------------------------|
| `uv init project_name`   | Initialize a new Python project     |
| `uv add <package>`       | Add a dependency                    |
| `uv run <script.py>`     | Run a Python script with dependencies |
| `uv pip freeze`          | Freeze installed packages           |
| `uv pip install -r requirements.txt` | Install from requirements file |

---

Happy building! ⚙️🚀
