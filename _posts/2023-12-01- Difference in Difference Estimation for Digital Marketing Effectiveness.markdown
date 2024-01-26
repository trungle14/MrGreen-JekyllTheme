---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_did
title: " Difference in Difference Estimation for Digital Marketing Effectiveness"

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Trung Le
# multiple category is not supported
category: Sharing
# multiple tag entries are possible
tags: [jekyll, example post, sample, test]
# thumbnail image for post
img: ":san diego.png"
# disable comments on this page
#comments_disable: true

# publish date
date: 2024-01-10 10:04:30 +0900

# seo
# if not specified, date will be used.
#meta_modify_date: 2024-01-10 10:04:30 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# please use the "image_viewer_on" below to enable image viewer for individual pages or posts (_posts/ or [language]/_posts folders).
# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in _data/conf/main.yml.
#image_viewer_on: true
# please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (_posts/ or [language]/_posts folders).
# image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in _data/conf/main.yml.
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---


<!-- outline-start -->

 ***Before diving into Difference in Difference, let's start with small example, since I am a football lover, my question might be determining whether Lionel Messi's signing with FC Miami led to a rise in Florida's tourism, a trend that surpasses just a general increase in interest in Miami. We'll use this scenario to understand the impact of a significant sports event on tourism.***

*The DiD approach is typically utilized for evaluating the effects of large-scale policy changes or interventions. Examples include examining the influence of immigration policies on unemployment rates, the impact of changes in firearm laws on crime statistics, or evaluating how a marketing campaign affects user engagement. In these situations, there's always a timeframe before the intervention and one following it, where the goal is to discern the specific effects of the intervention from the overarching trend.*


{:data-align="center"}

<!-- outline-end -->


```{r}
setwd ("/Users/Trung/Downloads")
data = read.csv('did_sponsored_ads.csv')
treatment_week = c(10,11,12)
data <- data %>% mutate(treatment = ifelse(platform == 'goog',1,0),
                       after = ifelse(week %in% treatment_week,1,0),
                       total_traffic = avg_spons + avg_org)


google_Ad = data %>% filter (platform=="goog")
#Plotting the histogram for total clicks on Google
hist(google_Ad$total_traffic)
```
