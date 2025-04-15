# 🕷️ Tasnim Crawler

A simple multithreaded web crawler that scrapes news article titles and content from [Hamshahri Online](https://www.hamshahrionline.ir/) and stores the results in a CSV file.

## 📌 Overview

This Python project uses:

- `requests` and `BeautifulSoup` for HTTP requests and HTML parsing
- `concurrent.futures.ThreadPoolExecutor` for multithreaded crawling
- `pandas` to manage and export the scraped data

---

## 🧠 How It Works

1. `get_links()`:
   - Scrapes all anchor (`<a>`) tags from the homepage.
   - Filters for URLs containing the word "news".
   - Appends the root URL to relative paths.

2. `get_info(url)`:
   - Fetches the HTML content of a given news article.
   - Extracts the title and visible text.

3. `TasnimCrawler()`:
   - Calls `get_links()` to collect article URLs.
   - Uses multithreading to scrape each article in parallel.
   - Stores the data in a Pandas DataFrame and exports it to `tasnim.csv`.

---

## 📁 File Structure

```
.
├── get_links.py       # Contains get_links() function
├── get_info.py        # Contains get_info() function
├── main.py            # Contains TasnimCrawler() function and runs it
├── tasnim.csv         # Output CSV with news data
└── README.md          # Project documentation
```

---

## 🚀 Usage

1. **Install dependencies**:

```bash
pip install requests beautifulsoup4 pandas
```

2. **Run the crawler**:

```bash
python main.py
```

3. **Output**:
   - A CSV file named `tasnim.csv` will be created containing:
     - `url` – the article's URL
     - `title` – the page title
     - `text` – the extracted full text

---

## ⚠️ Notes

- The crawler is currently hardcoded to work with `https://www.hamshahrionline.ir/`. You can modify the `url_root` parameter in `get_links()` to target other websites (ensure they're structured similarly).
- Be respectful of websites' terms of service and do not overload their servers.


---

## 📄 License

This project is open-source and free to use.

