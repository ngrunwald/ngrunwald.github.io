---
layout: post
title: "Introducing Gavagai"
date: 2013-02-18 19:00
comments: true
categories: clojure
tags: gavagai, clojure, rome, clj-rome, rss, atom
---
This is the story of two countries. One of them, Clojureland, is newly
founded. It has a very egalitarian society, everyboby is willing to
talk to you casually and answer your questions in the same way,
regardless of his job or status. The other country, Javaland, has a
rigid class system, and an intricate system of courtesy. In order to
ask a question to anyone and have him answer with some info or data,
you need to know to which of many classes he belongs to. You also need
to know who his ancestors are and what classes *they* belong to. If
you do not talk to him in the specific way he expects, he will not
answer you at all.  

And so it is that when young students from the new land travel to see
the old masters to get their wisdom, they get bored and irrate quite
quickly. They say, "Why should I care if the old schmuck wants to call
his method *getName* or *getLabel*? And why can't I ask him directly
about the names?" And they go back to their land and try to reinvent
the wisdom of their forebearers in their own data-driven way. Which is
not bad, but probably not the fastest path to progress either.  

{% img right /images/white_rabbit.jpg 320 214 Gavagai %}
But there is another way. What the students need is a way to ask old
masters questions in their own way. What they need is a *translator*.
Let me introduce you to it. Its name is
[gavagai](https://github.com/ngrunwald/gavagai) and it is a cute white
rabbit. It is also a parable about the
[indeterminacy of translation](http://en.wikipedia.org/wiki/Indeterminacy_of_translation).
It acts as a translation dictionary, and helps you get your data out
of Javaland.  

Let's take an exemple. Let's say you want to parse a RSS feed. It is
only XML, so theoretically you can easily parse it directly in
Clojure. But in fact they are many formats (RSS 0.9, RSS 2.0, Atom,
etc.). Also, the Web is a wild place, and you get all sort of junk
and malformed fields you have to account for in your parsing. All in
all, this is dreary work, and you soon hope someone else had done it
for you.  

Well someone has. [ROME](http://rometools.org/) can parse most of what
you can throw at it. Let's see how we can go about getting all the
post titles and dates in a feed.  

```
(use 'gavagai.core)
(require 'clojure.java.io :as io)
(import 'com.sun.syndication.io.SyndFeedInput)

 (let [reader (io/reader arg)
      feed (.build (SyndFeedInput.) reader)
      entries (.getEntries feed)]
  (map #(array-map :title (.getTitle %)
                   :published-date (.getPublishedDate %))
       entries))
```

Not bad, but notice how verbose it would become rather cumbersome if
we wanted more keys. We have a great function to do this,
`select-keys`, but we need a Clojure data structuire to use it on.
That's where gavagai comes in.  
```
(def feed-translator
  (gav/register-converters
   [["com.sun.syndication.feed.synd.SyndFeedImpl"]
    ["com.sun.syndication.feed.synd.SyndEntryImpl"]]))

(let [reader (io/reader arg)
      feed (translate feed-translator (.build (SyndFeedInput.) reader))]
  (map #(select-keys % [:title :published-date]) (:entries feed)))
```

That's much better and easy to read. And that's how gavagai works in a
nutshell. You define a translator by registering the class names
you're interested in with `register-converters`, then you call
`translate` with it and an object, and you get back a translated
Clojure data structure. It acts a bit like the core function `bean`.
But it is recursive, configurable, and faster because most
reflection happens only once when registering the classes in the
translator. It is also quite easy to use from the REPL, which makes it
great to explore big Java APIs.  

So, I invite you to look at the README of
[gavagai](https://github.com/ngrunwald/gavagai) for further details.
There are a lot of options. You can also look at the tests for more examples.  

And if you need to parse some feed and you wonder if this exemple has
been turned into a true wrapper, the answer is yes. It's called
[clj-rome](https://github.com/ngrunwald/clj-rome) and it is only 60
lines long thanks to gavagai. This code is a good exemple of real
production usage of gavagai.  
