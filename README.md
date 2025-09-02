# Web-Scraper
Let’s scrape the titles of articles from a simple blog or news site. For this example, we’ll use https://quotes.toscrape.com , a site designed for scraping practice.
🔹 Step 1: requests.get(url)
      🔹This fetches the content of the webpage using the HTTP GET method.
      🔹Returns a response object containing all the HTML.

🔹 Step 2: Status Code Check
      🔹response.status_code checks if the request was successful (200).
      🔹If not, we exit early.

🔹 Step 3: Parsing HTML
      🔹BeautifulSoup(response.text, 'html.parser') parses the HTML content.
      🔹Now we can navigate and search through the HTML as a Python object.

🔹 Step 4: Find HTML Elements
      🔹soup.find_all('div', class_='quote') returns a list of all divs with class quote.
      🔹These are the containers for each quote on the page.

🔹 Step 5: Extract Text
  🔹For each quote:
       .find('span', class_='text') gets the quote content.
       .find('small', class_='author') gets the author name.
       .get_text() extracts the text part only (removes tags).
