---
layout: page
title: Twitter geo project
---

Like all good projects, the idea for this one came from an idle Tuesday afternoon conversation with a friend; a friend who had an interesting idea for using twitter data to find out where people of a tax-averse nature were hiding their money. He asked me "would it be possible to map the places that someone on twitter talks about?" and a project was born!

It turns out that this idea can also have other, socially-valuable uses, like mapping the spread of disease outbreaks (e.g. Ebola in west Africa, influenza in Europe) by mapping the places that people talk about in tweets with a particular hashtag. E.g. "I feel awful right now, staying home in Bern #flu". Which is nice, and how I ended up meeting some very pleasant epidemic modellers in Geneva.

My original implementation was created before the 2018 extension of tweets, and followed in the footsteps of the excellent book [Mastering social media mining in Python](https://www.packtpub.com/big-data-and-business-intelligence/mastering-social-media-mining-python) by [Marco Bonzanini](https://marcobonzanini.com/about/). It was intended for you to supply the twitter handle of a particular account, and would produce a zoomable [Folium](https://python-visualization.github.io/folium/) map of the places people had tweeted about, with a mouseover of what they had said. The reason for the mouseover was pretty simple, it turns out that there are an awful lot of places in the world, and particularly in the US, which have stolen people's names (e.g. Anna TX, Anna IL etc). So to avoid the false positives of someone talking about their sister Anna, and being marked as having visited Illinois, we needed to surface this information on the map, but including the text of the original tweet.

Worse, there is also the issue that [geopy's](https://geopy.readthedocs.io/en/stable/) Geotext module is very good, but only spots the city name e.g. "Paris", but of course is unable to know if you mean "Paris, France" or "Paris, Texas". Again, the only way I could see out of this bind was to use a decent data visualization so that that human confronted with this information could decide whether it seemed correct or not.
