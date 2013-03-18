---
layout: post
title: Ściągawka z GFM
published: "3 marca 2013"
tags: [jekyll, example]
description: "Przykładowy post"
---

<blockquote>
<img src="{{ site.baseurl }}/images/alan-perlis.png" alt="[Alan Perlis]" />
<p>
  Dealing with failure is easy: Work hard to improve. Success is also
  easy to handle: You've solved the wrong problem. Work hard to improve.
</p>
<p class="source">— Alan Perlis</p>
</blockquote>

# {{ page.title }}

Posty wpisujemy używając notacji
[Github Flavored Markdown](https://help.github.com/articles/github-flavored-markdown).
Notacja Markdown jest opisana
w artykule [Markdown: Syntax](http://daringfireball.net/projects/markdown/syntax)
na blogu Johna Grubera  „Daring Fireball”.

Na stronie [Markdownr] [] można wpisywać tekst w notacji Markdown
w jednym okienku, mając w drugim — podgląd na skonwertowany na
HTMl tekst.

[markdownr]: http://markdownr.com/ "markdown online previewer"

## Podkolorowywanie kodu

Kod wpisujemy tak:

<pre>&#x60;&#x60;&#x60;ruby
module Invisibility
  def hide
    @visible = false
  end
  def show
    @visible = true
  end
end
&#x60;&#x60;&#x60;
</pre>

A tak to wygląda po podkolorowaniu:

```ruby
module Invisibility
  def hide
    @visible = false
  end
  def show
    @visible = true
  end
end
```

Do kolorowania kodu Jekyll korzysta z programu
[pygmentize](http://pygments.org/docs/cmdline/).
Po instalacji tego programu polecenie:

```sh
pygmentize -L lexers
  ...
  * css+erb, css+ruby:
  * erb:
  * js+erb, javascript+erb, js+ruby, javascript+ruby:
  * rhtml, html+erb, html+ruby:
  * xml+erb, xml+ruby
  ...
```
wypisze nam listę nazw języków programowania rozpoznawanych
przez *pygmentize*.
