# Web-Scraping-with-Python
A repository for review and don't forget some stuff. Learn how to find out to make Web Scraping with python language looking trought examples and more.

<img src="https://imgs.search.brave.com/s8sEuiauQLTvnDbuSuOP8Z35FqJf1y74BZQk3LF-uoI/rs:fit:621:249:1/g:ce/aHR0cHM6Ly9tZWRp/YS5naXBoeS5jb20v/bWVkaWEvbDN2UmZO/QTFwMHJ2aE1TdlMv/Z2lwaHkuZ2lm.gif">

# Web Scraping with Python [English] <img a style="width:48px;height:48px;" src="https://i.gifer.com/origin/a2/a225ed9bc58ac27682481cf443d43de1.gif">

### |What is Web Scraping
The Web Scraping is the art of get and gathe web information across from web connection. Generraly is useful for lots of purposes such as extract data, automate task, help people and anothers reasons. [For More Informmation](https://en.wikipedia.org/wiki/Web_scraping)

### |How to use in Python3

To make a web scrapinng in python we'll use 2 (two) importants libraries for it.

Libraries       |
-------------   |-
`BeautifulSOup` |
`urllib`		    |

# BeautifulSoup [Python Library]
Beautiful Soup is a Python library for pulling data out of HTML and XML files. It works with your favorite parser to provide idiomatic ways of navigating, searching, and modifying the parse tree. It commonly saves programmers hours or days of work. [Source](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)

### |Library Installation
```python3
pip install beautifulsoup4
```


### |Example 1.0
```python3
#!/usr/bin/env python3

from bs4 import BeautifulSoup
import requests

url = (
        "https://www.fakenamegenerator.com"
        )

request = requests.get(url).content

soup = BeautifulSoup(request, 'html.parser')

print (
        soup.title #or print(soup)
      )

```

[BeautifulSoup website](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)

### Example 1.1
A variable that contains the HTML content.
```python3
#!/usr/bin/env python3

# Step 1 - Importing library

from bs4 import BeautifulSoup

# Step 2 - Getinng The Content

html_content = """<html><head><title>The Dormouse's story</title></head>
<body>
<p class="title"><b>The Dormouse's story</b></p>

<p class="story">Once upon a time there were three little sisters; and their names were
<a href="http://example.com/elsie" class="sister" id="link1">Elsie</a>,
<a href="http://example.com/lacie" class="sister" id="link2">Lacie</a> and
<a href="http://example.com/tillie" class="sister" id="link3">Tillie</a>;
and they lived at the bottom of a well.</p>

<p class="story">...</p>
"""

# Step 3 - Making soup of the content (Soup from variable html_content)

soup = BeautifulSoup(html_content, 'html.parser')

# Step 4 Filtering the soup content from variable (soup)

print (
		soup.title
     )


```

Here are some simple ways to navigate that data structure:
```python3
soup.title
# <title>The Dormouse's story</title>

soup.title.name
# u'title'

soup.title.string
# u'The Dormouse's story'

soup.title.parent.name
# u'head'

soup.p
# <p class="title"><b>The Dormouse's story</b></p>

soup.p['class']
# u'title'

soup.a
# <a class="sister" href="http://example.com/elsie" id="link1">Elsie</a>

soup.find_all('a')
# [<a class="sister" href="http://example.com/elsie" id="link1">Elsie</a>,
#  <a class="sister" href="http://example.com/lacie" id="link2">Lacie</a>,
#  <a class="sister" href="http://example.com/tillie" id="link3">Tillie</a>]

soup.find(id="link3")
# <a class="sister" href="http://example.com/tillie" id="link3">Tillie</a>
```

Another common task is extracting all the text from a page:

```python3
print(soup.get_text())
# The Dormouse's story
#
# The Dormouse's story
#
# Once upon a time there were three little sisters; and their names were
# Elsie,
# Lacie and
# Tillie;
# and they lived at the bottom of a well.
#
# ...
```

## [Beautiful Soup Documentation](https://www.crummy.com/software/BeautifulSoup/bs4/doc/#beautiful-soup-documentation)

# urllib [Python Library]
Urllib package is the URL handling module for python. It is used to fetch URLs (Uniform Resource Locators). It uses the urlopen function and is able to fetch URLs using a variety of different protocols.

Urllib is a package that collects several modules for working with URLs, such as:

- urllib.request for opening and reading.
- urllib.parse for parsing URLs
- urllib.error for the exceptions raised
- urllib.robotparser for parsing robot.txt files

### To install
```python3
pip install urllib
```


## Example 1.0
```python3
import urllib.request
from urllib.request import Request, urlopen


request_url = Request(
        
        'https://www.google.com/',
         headers = {"User-Agent": "Mozilla/5.0"}
  
        )


result = urlopen(request_url)


print(result.read().decode())
```

## Example 1.1 - The 1.0 was based on:
```python3

import urllib.request
request_url = urllib.request.urlopen('https://www.geeksforgeeks.org/')
print(request_url.read())
```


## [urllib examples](https://www.geeksforgeeks.org/python-urllib-module/)

## [urllib documentation](https://docs.python.org/3/library/urllib.html)

# Avoiding problems

Now that you are aware to how to use the required kibraries you'll need to add some things in your code:

<img style="width:700px;height:300px;" src="https://imgs.search.brave.com/S65zLLDMhA_f_OrIwsacxtxQNc4XpK6Y8oFcnLrhXE0/rs:fit:800:600:1/g:ce/aHR0cHM6Ly9jZG4u/ZHJpYmJibGUuY29t/L3VzZXJzLzQwNDcw/MzQvc2NyZWVuc2hv/dHMvOTE3NjI3NS9t/ZWRpYS9iNDBlMGQ2/YzExNTYzNGE2MmVj/NTFjOWI2OGExNmYz/Zi5naWY.gif">

Was possible to see there are lots of ways to make web scraping, althought you will need the things bellow to avoid future problems.

- Use Headers on Request

headers = {"User-Agent": "Mozilla/5.0"}

- Use lxml for get strings and prevent from others issues.

features = "lxml"

## Final Result 
```python3
from urllib.request import Request, urlopen
from os import system as exe
from bs4 import BeautifulSoup

exe ("clear")

page = Request(

        "https://beautiful-soup-4.readthedocs.io/en/latest/",
                headers = {"User-Agent": "Mozilla/5.0"}

                        )

soup = BeautifulSoup(

    urlopen(page).read().decode(),
        features = "lxml"

    )

print(soup)

```

### An example of a sucessfuly web scrap news on site g1 from Brazil to get information.

```python3
from urllib.request import Request, urlopen
from os import system as exe
from bs4 import BeautifulSoup

exe("cl")

web = Request("https://g1.globo.com/", headers = {"User-Agent": "Mozilla/5.0"})


soup = BeautifulSoup(
          				  urlopen(web).read().decode(), "lxml"
					)

for x in (soup.find_all('a',{"class": "feed-post-link gui-color-primary gui-color-hover"})):

        print("Noticia: ", x.string)
        print("Link: ", x['href'], "\n")

```







**All Resources used/ Studied**

[Studing Mark Down](https://raw.githubusercontent.com/Al0nnso/Al0nnso/master/README.md)

[Studing Mark Down 2](https://raw.githubusercontent.com/Leandro-Leone/Leandro/main/README.md)

[Studing Mark Down 3](https://raw.githubusercontent.com/aboul3la/Sublist3r/master/README.md)

[How to filtrer a class with web scraping](https://stackoverflow.com/questions/5041008/how-to-find-elements-by-class)

[Studing BeautifulSoup Documentation](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)

[How to get a link by Tag](https://stackoverflow.com/questions/1080411/retrieve-links-from-web-page-using-python-and-beautifulsoup)

[Urllib Examples](https://www.geeksforgeeks.org/python-urllib-module/)

[Web scraping with Python urllib or requests](https://stackoverflow.com/questions/48246875/web-scraping-with-python-urllib-or-requests)

[I was thinking but did not use to translate for english with python. I might do it very soon.](https://search.brave.com/search?q=translate+to+english+in+python&source=desktop)

[TypeError: urlopen() got an unexpected keyword argument 'headers'](https://stackoverflow.com/questions/32071337/typeerror-urlopen-got-an-unexpected-keyword-argument-headers)
