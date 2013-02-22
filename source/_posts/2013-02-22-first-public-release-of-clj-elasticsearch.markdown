---
layout: post
title: "First public release of clj-elasticsearch"
date: 2013-02-22 15:55
comments: true
categories: clojure
tags: elasticsearch, clj-elasticsearch
---
I'm happy to announce the first public release of
[clj-elasticsearch](http://ngrunwald.github.com/clj-elasticsearch), a
Clojure wrapper for [Elasticsearch](http://www.elasticsearch.org/), the
distributed and easy to use search engine that probably needs no
introducing anymore. It exposes a very nicely done REST interface
which is the preferred way in most programming languages to access it.
[Elastisch](https://github.com/clojurewerkz/elastisch) is a nice
exemple of such a REST client in Clojure.  
However Elasticsearch can also be accessed through its native Java
library. It is not what could properly be called a client library, as
it used the same code and Maven artifact as the server itself. You can
communicate with the cluster of Elasticsearch nodes with the same
protocol they use internally. This may be somewhat faster and also
allows your client to use the same mechanisms of failover the cluster
uses. Even better, if you do not need distribution, you can embed the
node directly inside your app, to simplify deployment and
administration, and configuration.  
The Elasticsearch library is very extensive, a bit hard to navigate
(identifying the classes that are of interest for a client is not
always easy), and uses specific objects for everything. To build an
idiomatic Clojure wrapper above it, I took the path of using
compile-time reflection to generate as statically as possible the
Clojure functions needed to use the API.  
Some of the benefits this approach has allowed are:

  - The information gained from performing reflection on the Java
    classes allows to generate
    [docstrings](http://ngrunwald.github.com/clj-elasticsearch) that
    are detailed, up-to-date and always correspond exactly to the
    version of the elasticsearch lib used by the code.
  - Code that is more succint, and easier to test
  - It is reasonably fast. Some hasty and limited benchmark
    [here](https://github.com/ngrunwald/elasticsearch-bench) seems to
    suggest clj-elasticsearch is about 5 times faster than the REST
    API (with
    [Elastisch](https://github.com/clojurewerkz/elastisch))
  - You can use the lib in both sync and async style, and you can use
    async both through clojure-style Futures and callback passing,
    simply by using Elasticsearch native support for asynchronous
    operations. This allows even more performance gains.
  - Even though the Java API has seen some important class changes,
    clj-elasticsearch can use compile time reflection to provide a
    consistent Clojure API that is compatible with every Elasticsearch
    version since **0.19.0** up to now

I invite you to look at the
[project](https://github.com/ngrunwald/clj-elasticsearch) itself, the
extensive [docstrings](http://ngrunwald.github.com/clj-elasticsearch)
and the
[tests](https://github.com/ngrunwald/clj-elasticsearch/blob/master/test/clj_elasticsearch/test/client.clj)
to explore clj-elasticsearch API. This library has been partly written
at [Linkfluence](http://us.linkfluence.net/) and has seen over a year
of intensive production usage here, but of course we do not use every
function of Elasticsearch rich API, so bug reports and patches are
very welcome.  
