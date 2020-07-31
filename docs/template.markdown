---
layout: page
title: Template
permalink: /template/
exclude_from_search: true
---

# Template

------------------------------------------------------

**Markdown Cheatsheet [here](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)**

### Refer this [link](https://github.com/sheldonsebastian/StatisticsAndProgrammingQuickReference/blob/master/docs/template.markdown) to know how this page was created.

**1. Code Snippets**

  - Python: 

{% highlight python %} 
def foo(x):
	print("Hello", x)
​     
if __name__ == "__main__":
	foo("World")
{% endhighlight %}


  - r

{% highlight r %} 
library(gapminder)

library(dplyr)

library("ggplot2")

gapminder_2007<- gapminder %>% filter(year == 2007)

ggplot(gapminder_2007, aes(x= gapminder_2007$gdpPercap, y= gapminder_2007$lifeExp)) + geom_point()
{% endhighlight %}


  - Explore more supported languages [here](https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers)


**2. [Images](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#images) and [Jekyll Images](https://jekyllrb.com/docs/posts/#including-images-and-resources)**

Place all images in asset/images/ folder or place in desired folder, but that should not contain spaces!!

- From local source

![uploaded image](/assets/images/baby yoda.jpg)

- From online source

![online image](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Online Image")



**3. Links to other page**

**4. Links to external websites**
- Open in new tab
- Open in same tab

**5. [Tables](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#inline-html)**


| Col1        | Col2           | Col3  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| col 1 is | left-aligned      |    $1 |



**6. Gifs**


**7. Paragraphs**


**8. Youtube videos**


**9. [Different Text levels](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#headers)**


**10. [Lists](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#lists)**


**11. [Inline HTML](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#inline-html)**

