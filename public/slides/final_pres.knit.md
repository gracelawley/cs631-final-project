---
title: "Sentiment Analysis of a CHILDES corpus"
subtitle: "CS631: Final Presentation"
author: "Grace Lawley"
date: "June 18th, 2018"
output: 
  xaringan::moon_reader:
    css: [default, metropolis, metropolis-fonts]
    nature:
      highlightStyle: atelier-lakeside-light
      highlightLines: true
      countIncrementalSlides: false
---

# The Dataset

- Child Language Data Exchange System (CHILDES)  
  - Online repository of language acquisition data

- CHILDES → Eng-NA → **Kuczaj Corpus**
  - Longitudional Case Study
  - 1 target child: Abe
  - ~2 - ~5 years old
  - 210 transcripts (average of 810 words long)
---

# Getting the Raw Data

- Pulled down from the CHILDES database with the `childesr` package


```
##        id            speaker_id   utterance_order transcript_id 
##  Min.   :1169076   Min.   :3019   Min.   :  1.0   Min.   :3568  
##  1st Qu.:1188585   1st Qu.:3019   1st Qu.: 69.0   1st Qu.:3619  
##  Median :1204130   Median :3019   Median :138.0   Median :3658  
##  Mean   :1203150   Mean   :3019   Mean   :154.7   Mean   :3665  
##  3rd Qu.:1218038   3rd Qu.:3019   3rd Qu.:215.0   3rd Qu.:3711  
##  Max.   :1232753   Max.   :3019   Max.   :791.0   Max.   :3777  
##                                                                 
##    corpus_id     gloss             num_tokens         stem          
##  Min.   :40   Length:31982       Min.   : 0.000   Length:31982      
##  1st Qu.:40   Class :character   1st Qu.: 3.000   Class :character  
##  Median :40   Mode  :character   Median : 5.000   Mode  :character  
##  Mean   :40                      Mean   : 5.023                     
##  3rd Qu.:40                      3rd Qu.: 7.000                     
##  Max.   :40                      Max.   :60.000                     
##                                                                     
##  part_of_speech     speaker_code       speaker_name      
##  Length:31982       Length:31982       Length:31982      
##  Class :character   Class :character   Class :character  
##  Mode  :character   Mode  :character   Mode  :character  
##                                                          
##                                                          
##                                                          
##                                                          
##  speaker_role       target_child_id target_child_age target_child_name 
##  Length:31982       Min.   :3019    Min.   :28.79    Length:31982      
##  Class :character   1st Qu.:3019    1st Qu.:34.99    Class :character  
##  Mode  :character   Median :3019    Median :40.13    Mode  :character  
##                     Mean   :3019    Mean   :41.55                      
##                     3rd Qu.:3019    3rd Qu.:46.59                      
##                     Max.   :3019    Max.   :60.36                      
##                                                                        
##  target_child_sex       type            media_end        
##  Length:31982       Length:31982       Length:31982      
##  Class :character   Class :character   Class :character  
##  Mode  :character   Mode  :character   Mode  :character  
##                                                          
##                                                          
##                                                          
##                                                          
##  media_start         media_unit        collection_id collection_name   
##  Length:31982       Length:31982       Min.   :3     Length:31982      
##  Class :character   Class :character   1st Qu.:3     Class :character  
##  Mode  :character   Mode  :character   Median :3     Mode  :character  
##                                        Mean   :3                       
##                                        3rd Qu.:3                       
##                                        Max.   :3                       
##                                                                        
##  num_morphemes      language         corpus_name       
##  Min.   : 1.000   Length:31982       Length:31982      
##  1st Qu.: 4.000   Class :character   Class :character  
##  Median : 6.000   Mode  :character   Mode  :character  
##  Mean   : 5.845                                        
##  3rd Qu.: 8.000                                        
##  Max.   :65.000                                        
##  NA's   :63
```


