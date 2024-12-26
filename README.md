# CATCHY PRICE DETECTION SOFTWARE V1-2024 

![GitHub](https://img.shields.io/github/license/Tristan296/Catchy)
![Python](https://img.shields.io/badge/python-v3.8%2B-blue)

<p align="center">
  <img src="https://github.com/Tristan296/Catchy/assets/109927879/1b8a9eb5-e06d-4a27-89aa-8e5f1ef2c988" width="70%"></img>
</p>

# What is Catchy?
Catchy's is a smart web-scraping application designed to extract the cheapest products from various e-commerce sites. 

# How it works
It extracts product info including product names, prices, images, and a link to the website. Hardcoding selector pathways is a common method used by web scrapers to scrape information. The problem is that web developers frequently update 
these html selectors, which breaks the code. 

Catchy works on the structure of websites instead. By intelligently retrieving the product name from the url and scanning for a matching html element with this product name, we can find the product card that contains other details including the price. Since most websites place the name of the product near the price, we can then retrieve the neighbouring elements and check if they contain an inner child element with a price value.

The idea is for it to be able to compare pricing across multiple large ecommerce sites to get the best prices.  

# Features
- Retrieve product information from multiple e-commerce websites.
- Compare prices and details for the same product across different sources.
- Easy-to-use web interface.
- Utilizes aiohttp and BeautifulSoup libraries.

# Efficiency 
- Utilises `asyncio` asynchronous fetching of product information for improved performance.
- Utilises lxml for efficient parsing of soup
- When parsing for website links, SoupStrainer filters links in soup quickly.
- `aiohttp.ClientSession`:
  - Connection pooling: for faster subsequent requests to the same host
  - Concurrency: concurrently performing requests without blocking the execution of other tasks
- 3 second timeout for fetching links

# linkExtractor.py --> (Fatih)
# --> Goals
    - Link extractor must work flawlessly against the given websites:
        -Myer ( /p/ )                      
        -David Jones ( /product/ )         
        -BingLee ( /products/ )            
        -JB Hi-Fi ( /product/ )                  
        -OfficeWorks ( /shop/officeworks/p/ )               
        -Harvey Norman ( https://www.harveynorman.com.au/product-name-???-???? ) --> hard to extract                     
        -The Good Guys( /p/ ) --> same developer as harvey norman --> hard to extract  
        -Rebel Sport ( /p/ )  
        -JD sports
        -Nike
        -Addidas
        -Puma
        -Asics
        -Foot Locker
        -Insport

1- We must be able to get all product links with a certain tag
2- Store these in an array sorted alphabetically
3- Move these items into an excell sheet
4- Get every duplicate item, grab its store name and sort by its price
5- I will add more as we progress

# imageDisplayer.py --> (Tristan)
# --> Goals (You can enter some yourself)

1- Get links from my extractor and display the product name, price and image 
2- Put these details in a html/css file and siplay them on web
3- In PLAYGROUND I've created a file where you can test put your code so we won't mix up our work


# Supported websites
| Website       | Support     |
| -----------   | ----------- |
| Rebel Sport   |     ✅      |
|    MYER       |     ✅      |
| JB Hi-Fi      |     ✅      |
| JD-Sports     |     ✅      |
| Nike          |     ✅      |
| David Jones   |     ❌      |
| Office Works  |     ✅      |
| Bing Lee      |     ✅      |


# Modules needed to install to transfer list into pandas
* openpyxl --> pip install openpyxl
* pandas --> pip istall
* pip install xlsxwriter
* pip install pyxll
* pip install xlrd --> for excel support
