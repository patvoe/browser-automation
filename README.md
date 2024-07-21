# Browser Automation Homework

## Summary

This Jupyter notebook demonstrates how to automate browser interactions to extract real estate listings from Zillow using Playwright. The main tasks include opening the browser, hiding automation signs, visiting Zillow, searching for listings, extracting and parsing the listings, handling pagination, and saving the results.

### Key Steps

1. **Setup and Imports:**
   - Import necessary libraries like Playwright, Stealth, OS, Random, and Pandas.

2. **Open Browser:**
   - Define an asynchronous function to open the browser using Playwright and navigate to Zillow.

3. **Search Listings:**
   - Locate the search box, input the search term, and trigger the search.

4. **Extract Listings:**
   - Extract listing information such as price, address, beds, baths, and area.

5. **Handle Pagination:**
   - Check for the next page and continue extracting listings until all pages are processed.

6. **Save Results:**
   - Save the extracted listings to a JSON file.

7. **Parse Prices:**
   - Parse the prices from the listings and calculate statistics like the median price.

8. **Extra Credit:**
   - Additional tasks include calculating median price per square foot, identifying the realtor with the most listings, and highlighting listings over $1M.

### Code Snippets

- **Open Browser:**
  ```python
  async def open_browser():
      playwright = await async_playwright().start()
      browser = await playwright.firefox.launch(headless=False)
      page = await browser.new_page()
      await stealth_async(page)
      return browser, page
