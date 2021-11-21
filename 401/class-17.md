## 

###  What is Web Scraping?
* Web scraping is a proccess of  extracting data from websites. 
*  It is a form of copying in which specific data is gathered and copied from the web, typically into a central local database or spreadsheet, for later retrieval or analysis.

### New York MTA Data

![](https://miro.medium.com/max/291/1*5Hwlx8IZxJ0m7AIx0TnddA.png)

- Each date in the above image is a link to the .txt file that you can download.
- It would be torturous to manually right click on each link and save to your desktop. Luckily, there’s web-scraping!

***Important notes about web scraping:***
1. Read through the website’s Terms and Conditions to understand how you can legally use the data. Most sites prohibit you from using the data for commercial purposes.
2. Make sure you are not downloading data at too rapid a rate because this may break the website. You may potentially be blocked from the site as well.

### Inspecting the Website

* Right click on website page then click inspect.
* Once you’ve clicked on “Inspect”, you should see this console pop up.
![](https://miro.medium.com/max/875/1*rcQ4KRlp1fhMFUydVv5lMg.png)
* Notice that on the top left of the console, there is an arrow symbol.
> If you click on this arrow and then click on an area of the site itself, the code for that particular item will be highlighted in the console. I’ve clicked on the very first data file, Saturday, September 22, 2018 and the console has highlighted in blue the link to that particular file.

```html
<a href=”data/nyct/turnstile/turnstile_180922.txt”>Saturday, September 22, 2018</a>
```
* Notice that all the .txt files are inside the `<a>`
* after we decided that all files inside anchor tags we can start coding.
  
### Python Code

```python
import requests
import urllib.request
import time
from bs4 import BeautifulSoup

url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)
```

* Next we parse the html with BeautifulSoup so that we can work with a nicer, nested BeautifulSoup data structure
* 
```python
soup = BeautifulSoup(response.text, “html.parser”)
```
* We use the method .findAll to locate all of our <a> tags.

```python
soup.findAll('a')
```
![](https://miro.medium.com/max/728/1*G6YulYb5rczkVvmn7nbQ6g.png)
* we need then to get the actual link
```python
one_a_tag = soup.findAll(‘a’)[38]
link = one_a_tag[‘href’]
```
* saved the file locally
```python
download_url = 'http://web.mta.info/developers/'+ link
urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:])
```
* to avoid blocking from server we should write the following line to pause the code for 1 second.
```python
time.sleep(1)
```
### How to Scrape Websites Without Getting Blocked.

1. Respect Robots.txt this file exists in the root of website
2. Make the crawling slower, do not slam the server, treat websites nicely
3. Do not follow the same crawling pattern
4. Make requests through Proxies and rotate them as needed
5. Rotate User Agents and corresponding HTTP Request Headers between requests
6. Use a headless browser like Puppeteer, Selenium or Playwright
7. Beware of Honey Pot Traps
8. Check if Website is Changing Layouts
9. Avoid scraping data behind a login
10. Use Captcha Solving Services

### References 
[How to Web Scrape with Python in 4 Minutes](https://towardsdatascience.com/how-to-web-scrape-with-python-in-4-minutes-bc49186a8460)

[What is Web Scraping?](https://en.wikipedia.org/wiki/Web_scraping)

[How to scrape websites without getting blocked](https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/)