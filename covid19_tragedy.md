---
title: "Tragedy or Catastrophe: Cultural Responses to Covid-19"
excerpt: "Neural graph reveals ..."
tag: collection
header:
  overlay_color: "#000"
  overlay_filter: "0.2"
  overlay_image: /assets/images/header.jpg
excerpt: ""
---

Status: In Progress | First online: 06-05-2020 | Updated: 07-05-2020

___


**Authors** Kristoffer L. Nielbo, [Center for Humanities Computing Aarhus](http://chcaa.io/#/).

___


**This study has not yet been peer reviewed.**

## Background ##
Cultural responses to crises can be detected as changes associative patterns in media discourse. It has been shown that metionings of basic produce (e.g., potatoes, corn) in newspapers *and* advertisement are indicative of major social instability and war \[1\] and that types of crisis (natural vs. social) display type-specific dynamic signatures in large collections of lexical data \[2\]. To explore associative patterns under Covid-19 in the Danish public opinion, we trained simple [neural embeddings](https://www.tensorflow.org/tutorials/text/word_embeddings) to represent lexical level information in Danish newspaper articles from [*Politiken*](https://politiken.dk/) and used the representations to generate a hierearchical association graph that reflects semantic associations between words. As Covid-19 is developing, we are adding more newspapers from Denmark through the [HOPE-project](https://hope-project.dk/#/) and from other Scandinavian countries through the collaboration in [Nordic Digital Humanities Laboratory](https://centre-for-humanities-computing.github.io/Nordic-Digital-Humanities-Laboratory/).

## Methods ##
Data are collected from Politiken's online newspaper (by agreement w. JP/Pol) from October 2019 to April 2020 (*n*=16097). Before training each newspaper article was casefolded, lemmatized and non-alphabetic characters were removed. Neural embeddings were trained using the CBOW model architecture for speed. In order to build the association graph, we used angular distance to generate to word similarity graph of the entire lexicon. For subgraph (see fig. 1, 2) we queried the graph with a set of seed words (e.g., covid-19, pandemic) computed the *k* nearest words ("primary associations") for each seed and then the *m* nearest words ("secondary associations") for each of the *k* words. The Louvain method for community detection was used to partition the graph.  


## Results ##
To find generic cultural associations to covid-19 patterns, we initially seeded the model with \{*Covid-19*,*economy*,*research*,*society*\} (fig. 1). Uppercase words indicate primary association, while lowercase indicates secondary associations. We  can discern several association patterns from the sub-graph. Four distinct cluster emerge <span style="color:#f1c40f">**POLITICS**</span>, <span style="color:#626567">**SOCIETY**</span>, <span style="color:#2e86c1">**RESEARCH**</span>, <span style="color:#1abc9c">**COVID-19**</span>. First, politics and society (and economy) are highly interconnected, and second, issues reated to climate debate (climate politics, climate measures, climate battle) make up a substantial part of politics. This reflects that climate was indeed the overarching theme in the 2019 general election, where the liberal 'red bloc' (social democract, S-party) returned to power. Notice that while Politiken is independent of party, it does maintain a liberal stance. Third, reseach is a central node in the graph, that connects the research cluster to society, politics, and Covid-19. Similary, catasrophe and (health) crisis are highly have many connections from the Covid-19 cluster to society, research, and politics. One secondary association from the Covid-19 cluster that seems noteworthy is *tragedy*. While tragedy and catastrophe both signify an "unexpected negative events", catastophe points to the event-driven point of change in history (e.g., a war, earth quake or famine), while tragedy carries a more psychological tone (e.g., a personal conflict, moral failure). To further probe this catastrophe-tragedy complex in the context of Covid-19, we quried the graph with \{*Covid-19*,*catasrophe*,*tragedy*\} (fig. 2). The resulting sub-graph shows two clusters, one for <span style="color:#1abc9c">**TRAGEDY**</span> and one for <span style="color:#f1c40f">**CATASTROPHE**</span>. It appears that Covid-19 is strongly connected to the catastrophe together with climate and health crisis. Tragedy on the other hand pulls a range of associative patterns from the domains of high culture and fiction such as nightmare, metaphor and, even, infatuation. In stark contrast to the catastrophe cluster, several of the associations of tragedy have positive connotations (e.g., miracle, desire, possibility space). These two general associative patterns indicate overlapping yet distinct modes of discourse, where tragedy connects Covid-19 with personal and psyhological states and catastrophe connects with more societal and economic disasters.


## Conclusion ##
The catastrophe-tragedy complex spans associative patterns in cultural crisis responses to Covid-19. While the catasrophe pattern is primarily negative, the tragedy pattern has positive connotations. To facilitate the psychological coping process, we suggest that opinion formers, journalists, influencers, and other culturally influential actors utilize the positive potential in the "Covid-19 as a tragedy" pattern to counterbalance the predominantly negative sentiment of "Covid-19 as a catastrophe". 

![corona](/Nordic-Digital-Humanities-Laboratory/assets/images/graph_corona.png "corona-economy-politics-research")
*Fig. 1: ... a graph*

![tragedy](/Nordic-Digital-Humanities-Laboratory/assets/images/graph_tragedy.png "corona-crisis-tragedy")
*Fig. 2: .. another graph*

## Resources ##

Comments submitted @ [NDHL Website](https://github.com/centre-for-humanities-computing/Nordic-Digital-Humanities-Laboratory/blob/master/_portfolio/pol_c19_response.md)

Data available @ JP/Pol is the proprierter of the raw data. Please contact [CHCAA](mailto:chcaa@cas.au.dk?subject=[Tragedy]%comments) for access to derived data.

Source code available @ [CHCAA GitHub](https://github.com/centre-for-humanities-computing/Semantic-Kernel)


## References ##
1 M. Wevers, J. Gao, and K. L. Nielbo, “Tracking the Consumption Junction: Temporal Dependencies between Articles and Advertisements in Dutch Newspapers,” [http://arxiv.org/abs/1903.11461](arXiv:1903.11461) \[cs\].

2 J. Gao, J. Hu, X. Mao, and M. Perc, “Culturomics meets random fractal theory: insights into long-range correlations of social and natural phenomena over the past two centuries,” Journal of The Royal Society Interface, vol. 9, no. 73, pp. 1956–1964.

 




