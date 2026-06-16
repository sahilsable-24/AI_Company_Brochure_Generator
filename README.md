# 🤖 AI Company Brochure Generator

An AI-powered tool that automatically generates professional company brochures by scraping a company's website and using a large language model (LLM) to produce polished, structured marketing content.

---

## 📋 Overview

This project takes a company's website URL as input, scrapes its content and internal links, and then uses the OpenAI API to generate a compelling company brochure — ideal for prospective customers, investors, or recruits.

The workflow:
1. **Scrape** the company's homepage and relevant internal pages using `BeautifulSoup` and `requests`
2. **Extract** meaningful text content, filtering out scripts, styles, and other noise
3. **Feed** the scraped content to an LLM via the OpenAI API
4. **Generate** a well-structured, professional brochure in Markdown format

---

## 📁 Project Structure

```
AI_Company_Brochure_Generator/
│
├── Brochure_genrator.ipynb   # Jupyter Notebook — interactive step-by-step walkthrough
├── scrapper.py               # Web scraping utilities (fetch content & links)
├── main.py                   # Entry point for the application
├── pyproject.toml            # Project metadata and dependencies
├── uv.lock                   # Locked dependency versions (uv package manager)
├── .python-version           # Python version pin
├── .gitignore
└── README.md
```

---

## ✨ Features

- **Web Scraping** — fetches and cleans text from any public company website
- **Link Extraction** — discovers and follows internal links to gather more context
- **LLM-Powered Generation** — uses OpenAI's API to write a professional brochure from raw web content
- **Jupyter Notebook** — includes an interactive notebook for easy exploration and experimentation
- **Minimal & Clean** — lightweight dependency stack with no unnecessary overhead

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.12+ | Core language |
| `requests` | HTTP requests to fetch web pages |
| `BeautifulSoup4` (bs4) | HTML parsing and text extraction |
| `openai` | LLM API client for brochure generation |
| `uv` | Fast Python package manager |
| Jupyter Notebook | Interactive development and demo |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.12 or higher
- An [OpenAI API key](https://platform.openai.com/api-keys)
- [`uv`](https://github.com/astral-sh/uv) package manager (recommended) or `pip`

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/sahilsable-24/AI_Company_Brochure_Generator.git
   cd AI_Company_Brochure_Generator
   ```

2. **Install dependencies using `uv`**

   ```bash
   uv sync
   ```

   Or using `pip`:

   ```bash
   pip install beautifulsoup4 openai requests
   ```

3. **Set your OpenAI API key**

   ```bash
   export OPENAI_API_KEY="your-api-key-here"
   ```

   On Windows:
   ```cmd
   set OPENAI_API_KEY=your-api-key-here
   ```

### Usage

**Option 1 — Jupyter Notebook (Recommended for exploration)**

```bash
jupyter notebook Brochure_genrator.ipynb
```

Open the notebook and run the cells step by step to scrape a website and generate a brochure interactively.

**Option 2 — Python script**

```bash
python main.py
```

---

## 🔍 How It Works

### `scrapper.py`

Contains two core utility functions:

- **`fetch_website_contents(url)`** — Sends an HTTP GET request to the given URL, parses the HTML with BeautifulSoup, removes irrelevant tags (scripts, styles, images, inputs), and returns the page title + cleaned body text (truncated to 2,000 characters).

- **`fetch_website_links(url)`** — Fetches all `<a href>` links from a page, useful for discovering additional internal pages to enrich the brochure context.

### Brochure Generation

The scraped content is passed to an OpenAI LLM with a system prompt instructing it to act as a marketing expert. The model then produces a professional, structured brochure covering the company's mission, products/services, culture, and call to action.

---

## 📦 Dependencies

Defined in `pyproject.toml`:

```toml
dependencies = [
    "bs4>=0.0.2",
    "openai>=2.41.1",
    "requests>=2.34.2",
]
```

---

## ⚠️ Notes

- The scraper respects publicly accessible pages only. Do not use it on sites that prohibit scraping in their Terms of Service.
- Content is truncated to 2,000 characters per page to stay within LLM token limits. This can be adjusted in `scrapper.py`.
- The quality of the generated brochure depends on how much useful content is publicly available on the target website.

---

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request for bug fixes, new features, or improvements.

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 📄 License

This project is open source. See the repository for license details.

---

## 👤 Author

**Sahil Sable**
[GitHub](https://github.com/sahilsable-24)
