---
layout: page
title: "List of my Past Talks"
date: 2013-02-04 00:47
comments: false
sharing: true
footer: true
---
## Publications

### [Describing the Web in less than 140 characters (PDF)](http://www.aaai.org/ocs/index.php/ICWSM/ICWSM11/paper/view/2832/3242) 
*Fifth International AAAI Conference on Weblogs and Social Media*  
*Jul, 17th 2011*  
Links curation, that is, finding relevant information within the World-Wide-Web and its ever-growing amount of content is a crucial problem for information access. Hyperlinks recommendation has been for a long time a common way to share references between web users, be it by e-mail exchanges, instant messages or forums. We explore in this paper how Social Media extend this recommendation practice by focusing on the citation of hyperlinks on Twitter. We investigate how people deal with the strong limitation of 140 characters per message, showing that this constraint encourages people to perform a good synthesis of the content they are linking to. We take advantage of this practice to efficiently cluster the actual content of the linked pages with an algorithm based on lexical proximities between messages. Our method yields topical clusters that are consistent with the dynamics of user interests with no need to extract text from the pages themselves.  

### Traduire et refuser de traduire au cinéma : Etude statistique du cas des titres de films
*La traduction audiovisuelle : Approches pluridisciplinaires*  
*Jun, 19th 2008*

## Conference Talks

### [Introduction au Traitement Automatique des Langues avec Stanford CoreNLP et Clojure](http://act.osdc.fr/osdc2012fr/talk/4335)
*OSDC.fr 2012 at the Open World Forum*  
[*Video (in french)*](http://www.dailymotion.com/video/xun2gv_osdc-fr-2012-introduction-au-traitement-automatique-des-langues-avec-stanford-corenlp-et-clojure_tech?start=6#.UQ8BjyEo81I)  
La suite d'outils libres [Stanford CoreNLP](http://nlp.stanford.edu/software/corenlp.shtml) permet de mettre simplement en une une chaîne de traitement de données linguistiques. A partir des interviews réalisées par le site [usesthis.com](http://usesthis.com/), qui interroge diverses figures du monde du Logiciel Libre et du Web sur les outils (logiciels et matériel) qu'ils utilisent au quotidien, on tentera d'extraire mots-clés, noms de personnes et d objets et tonalité du discours, ainsi que de classifier les textes. On présentera à travers ces différents objectifs les étapes nécessaires pour traiter automatiquement du texte brut tel qu'on peut le collecter sur Internet.

### [Des outils et des hommes](http://journeesperl.fr/fpw2012/talk/4101)
*French Perl Workshop 2012*  
[*Video (in french)*](http://www.youtube.com/watch?v=DmT2Tou_k6U)  
Depuis janvier 2009, le site [usesthis.com](http://usesthis.com/) a réalisé et mis en ligne plus de 250 interviews de diverses figures du monde du Logiciel Libre et du Web (Richard Stallman, James Gosling, William Gibson, etc...), visant à leur faire présenter les outils (logiciels et matériels) qu'ils utilisent au quotidien. C'est donc un échantillon intéressant des bonnes pratiques. Nous présenterons dans un premier temps le code et les librairies permettant d'extraire sous une forme structurée les données du site. Ensuite, nous présenterons des statistiques sur les grandes tendances qui émergent de ce dataset, et différentes méthodes et outils pour les représenter.

### [Using Cascalog and Hadoop for rapid graph processing and exploration](https://archive.fosdem.org/2012/schedule/event/cascalog_hadoop_graph.html)
*FOSDEM 2012*  
[*Video (in english)*](http://www.youtube.com/watch?v=3czv_E9ALNE)  
Graphs are becoming increasingly popular as ways of modeling a wide variety of systems. As such, the label "graph processing" also covers a range of objectives and architectural constraints. At [Linkfluence](http://us.linkfluence.net), we use graph processing on datasets produced with very different systems (Web crawler, Twitter and Facebook API, feed aggregator, etc.) We spend a lot of time doing exploratory programming, trying to use our eclectic datasets in interesting ways, and processing our data in asynchronous workflows.  
We have come to see [Hadoop](http://hadoop.apache.org) and the processing framework [Cascalog](https://github.com/nathanmarz/cascalog) as essential tools in our toolbox when dealing with graphs, since it gives us architectural flexibility, scalability and the possibility of rapid prototyping.  
Cascalog is an open source framework built on top of Hadoop and [Cascading](http://www.cascading.org). Its syntactic and semantic roots come from Datalog and Prolog, which have been succesfully applied for a long time in the manipulation of graphs. Also, its ability to directly embed the expressive [Clojure](http://clojure.org) language allows to very easily define custom operations and ad-hoc processing.  
In this talk, we will present the framework, consider its advantages and drawbacks when compared to other approaches, show concrete exemples of usage for graph processing and how we use them to complement graph databases.  

### [Tools and Methods for Web Data Extraction](https://archive.fosdem.org/2011/schedule/event/webdataextraction.html)
*FOSDEM 2011*  
Panoramic view of the field of web data extraction with methods and libraries in various languages for efficient data extraction from HTML pages.  
Websites are one of the main source of data on the web. These websites can be classified in diverse categories (blogs, forums, news, etc.) This data is usually available only as part of html pages, which makes it hard to extract rich information from it. It is however often very desirable to differentiate navigation menu from content, or to extract metadata like date, title, author of the page content.  
This talk proposes to give a panoramic view of the field of web data extraction. It will show what are the problems encountered and the benefits that can be expected from better analysis of web pages for a variety of applications. It will present the different methods and libraries in various languages that allow to design efficient data extraction systems, from simple text heuristics to more sophisticated visual and classifiers-based approaches.

### [Présentation du langage Clojure](http://act.osdc.fr/osdc2010fr/talk/3048)
*OSDC.fr 2010*  
[*Video (in french)*](http://blip.tv/osdcfr-open-source-developers-conference-in-france/osdc-fr-2010-pr%C3%A9sentation-du-langage-clojure-nils-grunwald-4778673)  
Clojure est un langage de programmation dynamique relativement récent (2007) embarqué dans la machine virtuelle Java. Il a été conçu autour de quelques lignes directrices fortes: programmation fonctionnelle, structures de données non mutables disposant d'API simples et uniformes, évaluation paresseuse, très bonne intéropérabilitée avec le code Java natif, programmation concurrente facilitée. Tout en adoptant une syntaxe "à la LISP", il ne cherche pas la compatibilité avec les implémentations existantes (Common Lisp, Scheme) pour proposer une vision moderne et clarifiée du père des langages dynamiques.  
Il s'agit ici avant tout de proposer une introduction au langage mettant en avant ses particularités, ses points forts et son évolution récente.

