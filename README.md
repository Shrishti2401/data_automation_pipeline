## 📦 Day 4: Full Data Pipeline Automation

This project is the final piece of a 4-Day Python Data Automation Challenge.  
It demonstrates a fully automated end-to-end data pipeline using **Python** and **GitHub Actions**.

---

## 🚀 Project Summary

We automate the entire process of:

1. **Scraping product data** from a test website (BooksToScrape)
2. **Cleaning and transforming** that data
3. **Storing results** in CSV format
4. **Pushing updates automatically** to GitHub via GitHub Actions

No manual runs needed — the workflow executes every 5 minutes (or manually) and keeps track of which page was scraped last.

---

## 📁 Folder Structure

data_automation_pipeline/ 
        │ 
        
        ├── scrape_flipkart.py # Scraper script with smart pagination 
        
        ├── clean_transform.py # Cleans and transforms scraped data 
        
        ├── progress.txt # Tracks last scraped page (state memory) 
        
        ├── books_raw.csv # Appended scraped data 
        
        ├── books_cleaned.csv # Cleaned output 
        
        └── .github/ └── workflows/ └── scrape_pipeline.yml # GitHub Actions workflow file

---

## 🛠️ Tech Stack Used

- **Python 3.x**
- **BeautifulSoup4**
- **Pandas**
- **Requests**
- **GitHub Actions** (CI/CD + Scheduling)

---

## 🔄 Workflow Overview

### Step 1: [scrape_books.py](scrape_flipkart.py)
- Scrapes book info (title, price, rating) from [BooksToScrape](http://books.toscrape.com/)
- Only scrapes one page per run
- Tracks current page using [page_num.txt](page_num.txt)
- Appends new rows to [books_to_scrape.csv](books_to_scrape.csv)

### Step 2: [clean_transform.py](clean_transform.py)
- Loads [books_to_scrape.csv](books_to_scrape.csv)
- Removes unwanted characters from prices
- Converts price to float
- Drops incomplete rows
- Saves cleaned data to [books_cleaned.csv](cleaned_books.csv)

### Step 3: [GitHub Actions Workflow](.github/workflows)
-📄 File: [.github/workflows/scrape_pipeline.yml](.github/workflows/scrape_pipeline.yml)
- Scheduled to run **every 5 minutes**
- Automatically:
  - Runs both Python scripts
  - Commits any updates back to GitHub
  - Uses secure token authentication for pushing

---
## 📌 Learnings & Highlights
✅ Modular ETL pipeline using real-world tools

✅ Hands-free automation via GitHub Actions

✅ Progress-tracking for scraping (pagination memory)

✅ Secure Git commit automation using GitHub token

---

## 🔗Related Projects
-[Day 1: Web Scraping & Cleaning](https://github.com/Shrishti2401/Data_Automation_4_Days_Chalenge/tree/main/day1)

-[Day 2: Data Manipulation + SQL Automation](https://github.com/Shrishti2401/Data_Automation_4_Days_Chalenge/tree/main/day2)

-[Day 3: Tableau Dashboard](https://github.com/Shrishti2401/Data_Automation_4_Days_Chalenge/tree/main/day3)

---
## 🙋‍♂️ Want to Explore More?
This is part of a bigger challenge. Feel free to check out [my LinkedIn post](https://www.linkedin.com/posts/shrishti-agarwal-2a356a179_dataautomation-python-hackerrank-activity-7312849023315427329-otrC?utm_source=share&utm_medium=member_desktop&rcm=ACoAACpDdxsBKyiVKnfLLewO2siOKOBOcQ8V41o) or connect with me if you're curious about how it ties into data automation and analytics!






