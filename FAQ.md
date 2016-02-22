# Jekyll F.A.Q.s - Frequently Asked Questions (and Answers)

[What's News?](#whats-news) • 
[Themes / Templates](#themes--templates) • 
[Getting Help](#getting-help) • 
[Troubleshooting](#troubleshooting) •
[GitHub Pages](#github-pages) •
[History / Trivia](#history--trivia) •
[Meta](#meta)



## What's News?

#### Q: Where can I find the latest (and greatest) Jekyll news and goodies?

Check the official Jekyll news blog (web: [jekyllrb.com/news](http://jekyllrb.com/news)) 
or the Twitter page (t: [jekyllrb](https://twitter.com/jekyllrb)).

For detailed upcoming major and minor enhancements and bug fixes, see the [History page](https://github.com/jekyll/jekyll/blob/master/History.markdown) in the Jekyll repo.

For more Jekyll news see the Static Times news channel (t: [statictimes](https://twitter.com/statictimes)).

For more Jekyll goodies see the [Awesome Jekyll](https://github.com/planetjekyll/awesome-jekyll) bookmark list or the [Jekyll bookmark category](http://www.thenewdynamic.org/tool/jekyll/) at the (Static is) The New Dynamic site.


## Themes / Templates

#### Q: Where can I find themes?

Check the [Dr. Jekyll's Themes](https://drjekyllthemes.github.io/) directory or

See the [Themes wiki page](https://github.com/jekyll/jekyll/wiki/Themes) at the Jekyll repo site or

Search Goolge for [jekyll themes](http://google.com/?q=jekyll+themes) 


#### Q: Can I use Bootstrap with Jekyll?

Yes, of course. You can use any HTML starter template/boilerplate with Jekyll.

Jekyll (and GitHub Pages) has built-in support for SCSS, thus, if you use the Bootstrap SCSS version - Jekyll
will auto-build the `bootstrap.css` from the sources letting you change colors,  fonts and much more
in `_settings.scss`.
To get started see the `jekyll-bootstrap-theme` (github: [drjekyllthemes/jekyll-bootstrap-theme](https://github.com/drjekyllthemes/jekyll-bootstrap-theme)) - a ready-to-fork starter theme - as a (live) example.



## Getting Help 


#### Q: Where can I find help?

Use the official Jekyll talk forum (web: [talk.jekyllrb.org](https://talk.jekyllrb.com/)) 
to post your questions and find help on troubleshooting.

Ask your (Jekyll) friends!

For GitHub Pages see the [GitHub Pages Troubleshooting Help Pages](https://help.github.com/categories/github-pages-troubleshooting/)
for a start. 


#### Q: Where can I find Jekyll friends?

Look for a Jekyll (static site) user group in your city.

In Europe groups include:

- @ Vienna, Austria - **Vienna.html** (t: [viennahtml](https://twitter.com/viennahtml))

In America groups include:

- @ San Francisco, California -  **San Franciso Static Web Tech - SF SWT** (web: [staticwebtech.com](http://www.staticwebtech.com), meetup: [sf-static-web-tech](http://meetup.com/sf-static-web-tech/), t: [staticwebtech](https://twitter.com/staticwebtech))
- @ New York, New York - **The New Dynamic** (meetup: [The-New-Dynamic](http://meetup.com/The-New-Dynamic/))
- @ Austin, Texas - **Peanut Butter and Jekyll** (meetup: [PB-and-Jekyll](http://meetup.com/PB-and-Jekyll/))
- @ Denver, Colorado - **Denver Jekyll** (meetup: [denver-jekyll](http://meetup.com/denver-jekyll/))

If there's no Jekyll group yet in your city, why not start one! 
If not, try a local Ruby user group (be aware you might run into some Middleman fanatics ;-),
see the [Awesome Events Page @ Planet Ruby](https://github.com/planetruby/awesome-events) for a world-wide listing.  


## Troubleshooting

#### Q: The Markdown page (e.g. `welcome.md`) gets copied 1:1 to the `_site` folder without getting converted to HTML? Why?

Double check your front matter. Jekyll REQUIRES that your markdown page starts with a front matter section e.g.:

~~~
---
layout: page
title:  The Front Matters
---
~~~

Note: The front matter MUST start and end with three dashes e.g. `---` (not two `--` or four `----` etc.). As a rule: Without front matter there's no preprocessing, that is, conversion from Markdown (`.md`) to Markup (`.html`).


#### Q: Why are my page headings (e.g. `##Heading`) not rendered any longer?

Note: Most markdown converter REQUIRE a space between `##` and `Heading`, thus, change:

```
#Heading One
##Heading Two
```

to

```
# Heading One
## Heading Two
```

#### Q: Jekyll doesn't render Markdown when adding HTML tags?

Note: If you put your markdown inside an HTML block tag (e.g. `div`) - the default setting for Jekyll's markdown converter (e.g. kramdown) 
is to pass the text along as is, that is, without any conversion. Example:

```
<div>
A List:

- Apples
- Oranges
- Blueberries
</div>
```

Use the "magic" markdown attribute to turn on markdown conversion inside an HTML block tag e.g.:

```
<div markdown="1">
A List:

- Apples
- Oranges
- Blueberries
</div>
```

## Syntax Highlighting

#### Q: How can I get backtick fenced code blocks (e.g. \`\`\`) working (with kramdown)?

Use the GitHub-Flavored Markdown (GFM) parser / mode. Change your `_config.yml` settings to:

```
markdown: kramdown
 
kramdown:
  input: GFM
  hard_wrap: false
```

For more see the Official [GitHub-Flavored Markdown (GFM) Docu Page](http://kramdown.gettalong.org/parser/gfm.html).


### Q: How can I get backtick fenced code blocks (e.g. \`\`\`) working inside lists (with kramdown)?

The gist is that the indentation for the code block in lists is determined
by the column number of the first non-space character after the list item marker. Huh? 

Lets use some examples (note the leading spaces get replaced with dots e.g. `·` to help along):

_Bulleted List_

```
*·some text     =>  use 2 spaces indentation e.g.

  ```
   $ gem install beerdb
  ```

*···some text   =>  use 4 spaces indentation e.g.

    ```
    $ gem install beerdb
    ```
```

_Numbered List_

```
1.·some text    =>  use 3 spaces indentation

   ```
   $ gem install beerdb
   ```
```

**==> If you line up the fenced code block with the "natural" list indentation, it will work.**


For more examples, see the [syntax highlighter sandbox list page](http://planetjekyll.github.io/sandbox-syntax-highlighter/lists.html) - [(source)](https://github.com/planetjekyll/sandbox-syntax-highlighter/blob/gh-pages/lists.md).



#### Q: How can I turn on syntax highlighting in code blocks (with kramdown 'n' rouge)?

Use the `highlighter` and the `kramdown.syntax_highlighter` options. Change your `_config.yml` settings to:

```
highlighter: rouge

markdown: kramdown

kramdown:
  input: GFM
  hard_wrap: false
  syntax_highlighter: rouge
```


#### Q: How can I turn off syntax highlighting in code blocks (with kramdown 'n' rouge)?

Use the `kramdown.syntax_highlighter_opts.disable` option. Change your `_config.yml` settings to:

```
highlighter: rouge

markdown: kramdown

kramdown:
  input: GFM
  hard_wrap: false
  syntax_highlighter: rouge
  syntax_highlighter_opts:
    disable: true
```

For more see the Official [Rouge Syntax Highlighter Docu Page](http://kramdown.gettalong.org/syntax_highlighter/rouge.html).



## GitHub Pages

#### Q: What Jekyll plugins can I use on GitHub Pages?

See the [GitHub Pages Dependency Versions](https://pages.github.com/versions/) page 
listing all installed (white-listed) Jekyll Plugins.
In Aug/2015 the list includes:

- `jekyll-coffeescript` (github: [jekyll/jekyll-coffeescript](https://github.com/jekyll/jekyll-coffeescript)) - a CoffeeScript converter for Jekyll
- `jekyll-sass-converter` (github: [jekyll/jekyll-sass-converter](https://github.com/jekyll/jekyll-sass-converter)) - a basic Sass converter for Jekyll
- `jekyll-mentions` (github: [jekyll/jekyll-mentions](https://github.com/jekyll/jekyll-mentions)) - @mention support for your Jekyll site
- `jekyll-redirect-from` (github: [jekyll/jekyll-redirect-from](https://github.com/jekyll/jekyll-redirect-from)) - seamlessly specify multiple redirection URLs for your pages and posts
- `jekyll-sitemap` (github: [jekyll/jekyll-sitemap](https://github.com/jekyll/jekyll-sitemap)) - automatically generate a sitemap.xml for your Jekyll site
- `jekyll-feed` (github: [jekyll/jekyll-feed](https://github.com/jekyll/jekyll-feed)) - a Jekyll plugin to generate an Atom feed of your Jekyll posts
- `jemoji`  (github: [jekyll/jemoji](https://github.com/jekyll/jemoji)) - GitHub-flavored emoji plugin for Jekyll


## Liquid Templates

#### Q: How can I post (escape) code snippets that include curly brackets `{{ }}`?

Wrap your code snippets with `{% raw %}`..`{% endraw %}` tags. Example:

Before:

```liquid
{% assign words = content | number_of_words %}
{% if words < 360 %}
   1 min
{% else %}
   {{ words | divided_by:180 }} mins
{% endif %}
```

After:  

```liquid
{% raw %}
{% assign words = content | number_of_words %}
{% if words < 360 %}
    1 min
{% else %}
   {{ words | divided_by:180 }} mins
{% endif %}
{% endraw %}
```

Note: Unless escaped (with raw) `{{ }}` and `{% %}` get processed by Jekyll 
as Liquid template tags/directives/macros.



## History / Trivia

#### Q: Why is the Jekyll static site generator called Jekyll (and not Hyde or [your name here])?

Tom Preston-Werner started to put together some Ruby scripts that let you
"[Blog Like a Hacker](http://tom.preston-werner.com/2008/11/17/blogging-like-a-hacker.html)" back in 2008
and published the package as Jekyll with 
the tagline "Transform your text into a monster" and a black and white theme. 

The name is inspired by "[The Strange Case of Dr. Jekyll and Mr. Hyde](http://drjekyllthemes.github.io/jekyll-book-theme/)" - a novella written by 
Scottish author Robert Louis Stevenson first published in 1886 in London. 
Why? Read the novella online - generated using the Jekyll world classics book theme ;-) 
Spoiler alert:  Dr. Jekyll and Mr. Hyde is one and only one person. 




## Meta

**License** 

The Jekyll FAQs is dedicated to the public domain. 
Use it as you please with no restrictions whatsoever.

**Questions? Comments?**

Post them to the [wwwmake forum](http://groups.google.com/group/wwwmake). Thanks!

