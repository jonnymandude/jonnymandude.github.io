---
layout: post
title: A Game of Numbers? An Exploration of the 2023 QB Class
subtitle: Using Deep Learning to predict the draft position ouf our newest QB crop
cover-img: /assets/img/kc_draft.webp
thumbnail-img: /assets/img/strong_levis.webp
gh-repo: jonnymandude/QBR_scraper
tags: [ml, nfl, ]
---

Art or Science? Drafting a quarterback in the NFL is an impactful decision. The fate of a GM, coach and, in extreme cases, franchise lie within the prudence of the selection. In an effort to cut through the noise and chatter from pundits and fans alike, we'll see if we can stitch together a numerical moel that predicts a QBs draft position in their respective class. 

## Methodology

Using a combination of advanced statistics and combine measurables, we'll attempt to make sense of who is the cream of the 2023 crop. Here are the key metrics used: 


| Statistic | Description | 
| :------ |:--- |
| QBR | Adjusted Total Quarterback Rating, which values the quarterback on all play types on a 0-100 scale adjusted for the strength of opposing defenses faced. |
| PAA | Number of points contributed by a quarterback, accounting for QBR and how much he plays, above the level of an average quarterback. | 
| PLAYS | Plays on which the QB has a non-zero expected points contribution. Includes most plays that are not handoffs. | 
| EPA | Total expected points added with low leverage plays, according to ESPN Win Probability model, down-weighted. | 
| PASS | Expected points added on pass attempts with low leverage plays down-weighted. |
| RUN | Clutch-weighted expected points added through rushes | 
| SACK | Expected points added on sacks with low leverage plays down-weighted. | 
| PEN | Expected points added on penalties with low leverage plays down-weighted. | 
| RAW | Raw Total Quarterback Rating, which values quarterback on all play types on a 0-100 scale (not adjusted for opposing defenses faced) | 


The results? Not terribly predictive. [Take a look](https://www.kaggle.com/code/jglazier22/nfl-draft-exploration-a-qb-s-tale). As is the case with most social phenomena, we're not able to formulaically model the patterns that result in pick outcomes. The problem we're faced with is two-fold. 

1. Lack of Data

We don't have years of information on thousands of QB selections. Furthermore, the game evolves and statistics that were useful in the 90s are no longer useful in the modern era. In addition to that, not all advanced statistics are alike. Is Clayton Tune's passing yards against non Power 5 defenses as impressive as Anthony Richardson's performances within the SEC? What about comparing Will Levis against Stetson Bennett in the same conference? The quality of their rosters are highly distinct. 

Another aspect of this data set that is sorely missing is additional combine statistics. The combine is a great equalizer. By including this, we' have a standardized test of sorts amongst players

2. Interpretation

Many PFF stats and advanced stats are plagued with human interpretation. This makes it such that we plague these numbers with non-objective bias. In the event that we accurately diagnose Josh Allen as an elite passer despite underwhelming college numbers, our interpretations are accurate corrections. When we use this same thesis to justify a Paxton Lynch-esque selection, we no longer are quite so slick. 



## 2023 Results

There are a few QBs that the model loved. The model felt this should've been the draft order: 

- Hendon Hooker
- Anthony Richardson
- Clayton Tune
- DTR
- CJ Stroud

Very interesting how the model loves Richardson. It appears as though there is overweighting on the ability to run and the raw college QBR. Nothing crazy, but we would do well to incorporate some analysis of throwing ability. Some overall team metrics would be incredibly helpful as well. This would bring Bryce back into the fray.

One of the main takeaways of all of this is the imprecision and the lack of the ability to reduce a QB down to their raw numbers. My recommendation, watch the tape. Richardson's does not disappoint: 

<iframe width="560" height="315" src="https://www.youtube.com/embed/1JuZdq8iW-I" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>{: .mx-auto.d-block :}


If you're really curious about what a true number one pick looks like, look no further than the mild man from Palo Alto: 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N5STc2_bM7k" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>{: .mx-auto.d-block :}

