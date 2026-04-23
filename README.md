# Github-Trending-Cybersecurity-Tools-Scraper
A Python-based utility that scrapes the [GitHub Trending](https://github.com/trending) page for the latest popular cybersecurity tools and logs them to a CSV file for historical tracking.

## Features
- **Automated Scraping:** Fetches the top trending repositories daily.
- **Data Logging:** Saves results to `trending_tools.csv` with a timestamp for each entry.
- **Data Integrity:** Keeps a log of what was trending, allowing for future analysis of tool popularity over time.

## Getting Started

### Prerequisites
You need Python installed. Install the required libraries using pip:

```bash
pip install requests beautifulsoup4


## Sample Output
Here is what a typical entry in `trending_tools.csv` looks like:

```csv
Date,Tool Name,Description
2026-04-23,ToolName1,A powerful network forensic analysis utility.
2026-04-23,ToolName2,Automated vulnerability scanner for web apps.