# Jekyll FAQs - Frequently Asked Questions (and Answers)

[What's News?](#whats-news) • 
[Themes / Templates](#themes--templates) • 
[Getting Help](#getting-help) • 
[Troubleshooting](#troubleshooting) •
[GitHub Pages](#github-pages) •
[History / Trivia](#history--trivia) •
[Meta](#meta)



## What's News?

**Q**: Where can I find the latest (and greatest) Jekyll news and goodies?

**A**: 

- Check the official Jekyll news blog (web: [jekyllrb.com/news](http://jekyllrb.com/news)) 
  or the Twitter page (t: [jekyllrb](https://twitter.com/jekyllrb)).
- For detailed upcoming major and minor enhancements and bug fixes, see the [History page](https://github.com/jekyll/jekyll/blob/master/History.markdown) in the Jekyll repo.
- For more Jekyll news see the Vienna.html news page (t: [viennahtml](https://twitter.com/viennahtml)).
- For more Jekyll goodies see the [Jekyll bookmark category](http://www.thenewdynamic.org/tool/jekyll/) at the (Static is) The New Dynamic site.


## Themes / Templates

**Q**: Where can I find themes?

**A**:

- Check the [Dr. Jekyll's Themes Directory](https://drjekyllthemes.github.io/) or
- See the [Themes Wiki Page](https://github.com/jekyll/jekyll/wiki/Themes) at the Jekyll repo site or
- Search Goolge for [Jekyll Themes](http://google.com/?q=jekyll+themes) 


## Getting Help 


**Q**: Where can I find help?

**A**:

- Use the official Jekyll talk forum (web: [talk.jekyllrb.org](https://talk.jekyllrb.com/)) 
  to post your questions and help on troubleshooting.
- Ask your (Jekyll) friends!


For GitHub Pages see the [GitHub Pages Troubleshooting Help Pages](https://help.github.com/categories/github-pages-troubleshooting/)
for a start. 


**Q**: Where can I find Jekyll friends?

**A**: Look for a Jekyll (static site) user group in your city. The first one in Europe 
started in Vienna called [Vienna.html](https://twitter.com/viennahtml).

If there's no Jekyll group yet in your city, why not start one! 
If not, try a local Ruby user group (be aware you might run into some Middleman fanatics ;-),
 see the [Awesome Events Page @ Planet Ruby](https://github.com/planetruby/awesome-events) for a world-wide listing.  


## Troubleshooting

**Q**: The Markdown page (e.g. `welcome.md`) gets copied 1:1 to the `_site` folder 
without getting converted to HTML? Why?

**A**: Double check your front matter. Jekyll REQUIRES that your markdown page starts with a front matter section e.g.:

~~~
---
layout: page
title:  'The Front Matters'
---
~~~

Note: The front matter MUST start and end with three dashes e.g. `---` (not two `--` or four `----` etc.). As a rule: Without front matter there's no preprocessing, that is, conversion from Markdown (`.md`) to Markup (`.html`).



## GitHub Pages

**Q**: What Jekyll plugins can I use on GitHub Pages?

**A**: See the [GitHub Pages Dependencies Version Page](https://pages.github.com/versions/) 
listing all installed (white-listed) Jekyll Plugins.
In Aug/2015 the list includes:

- `jekyll-coffeescript`
- `jekyll-sass-converter`
- `jekyll-mentions`
- `jekyll-redirect-from`
- `jekyll-sitemap`
- `jekyll-feed`
- `jemoji`  (github: [jekyll/jemoji](https://github.com/jekyll/jemoji)) - GitHub-flavored emoji plugin for Jekyll



## History / Trivia

**Q**: Why is the Jekyll static site generator called Jekyll (and not Hyde or <your name here>)?

**A**: Tom Preston-Werner started to put together some Ruby scripts that let you
"[Blog Like a Hacker](http://tom.preston-werner.com/2008/11/17/blogging-like-a-hacker.html)" back in 2008
and published the package as Jekyll with 
the tagline "Transform your text into a monster" and a black and white theme. 

The name is inspired by "[The Strange Case of Dr. Jekyll and Mr. Hyde](http://drjekyllthemes.github.io/jekyll-book-theme/)" - a novella written by 
Scottish author Robert Louis Stevenson and first published in 1886 in London. 
Why? Read the novella online - generated using the Jekyll world classics book theme ;-) 
Spoiler alert:  Dr. Jekyll and Mr. Hyde is one and only one person. 




## Meta

**License** 

The Jekyll FAQs is dedicated to the public domain. 
Use it as you please with no restrictions whatsoever.

**Questions? Comments?**

Post them to the [jekyll talk forum](https://talk.jekyllrb.com). Thanks!

