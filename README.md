# Hotel Market Data Scraper – Booking.com (Yogyakarta)

## 📌 Project Description

### Problem
Booking.com provides rich hotel information (e.g. name, price, rating, location), but **does not offer an open API**, making it difficult to collect structured data for analysis. Manual data retrieval is time-consuming, error-prone, and not scalable.

### Goals
This project aims to:
- Automate hotel data extraction from Booking.com (focused on Yogyakarta, July 2024)
- Collect structured data: hotel name, nightly price, location, user review count, average rating, and star classification
- Build a foundational dataset that supports further analysis such as price trends, market segmentation, and customer preference insights

### Insights
- Booking.com uses **dynamic loading with infinite scroll**, which cannot be scraped with standard `requests` methods.
- Selenium is required to render and scroll the page, while BeautifulSoup helps extract structured content from HTML.
- Key hotel information is nested within specific HTML classes (e.g. `.aa97d6032f`).

### Dependency Variables
- Scroll height consistency (used to determine end-of-page)
- HTML class structure (subject to change by Booking.com at any time)
- Page load time and JavaScript rendering behavior
- Geolocation (hotel location filter: Yogyakarta, Indonesia)
- Booking date filter (hotels available for 19–20 July 2024)

### Advice / Conclusion
- Web scraping is a powerful workaround when APIs are unavailable, but **requires constant monitoring** due to potential DOM changes.
- Always check legality and respect robots.txt and terms of service.
- Cleaned data is stored in CSV format and ready to be used for dashboards, analytics, or integration into a broader data pipeline.
- For scalable use, consider implementing error handling, proxies, and scheduling.

---

## 🛠️ Dependencies

To run this project, install the following libraries:

```bash
pip install selenium
pip install beautifulsoup4
pip install pandas
