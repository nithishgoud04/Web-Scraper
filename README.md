import requests
from bs4 import BeautifulSoup

url = 'https://quotes.toscrape.com'
response = requests.get(url)

if response.status_code == 200:
    print("Successfully fetched the webpage!")
else:
    print("Failed to retrieve the webpage:", response.status_code)
    exit()

soup = BeautifulSoup(response.text, 'html.parser')

quotes = soup.find_all('div', class_='quote')

for idx, quote in enumerate(quotes, start=1):
    quote_text = quote.find('span', class_='text').get_text()
    author = quote.find('small', class_='author').get_text()
    print(f"{idx}. \"{quote_text}\" - {author}")
