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



# Business Overview
Bazaar.com, a prominent online retailer in the United States, has established a significant presence in digital advertising. This includes a strong focus on display advertising as well as search engine advertising, with a particular emphasis on running paid search ads across platforms like Google and Bing. The paid advertisements by Bazaar are categorized primarily into two distinct groups based on the keywords used: branded and non-branded. Branded keywords incorporate the 'Bazaar' brand name, examples of which include 'Bazaar', 'Bazaar shoes', 'Bazaar clothes', and similar phrases. In contrast, non-branded keywords are those like 'shoes', 'dress', and other terms that do not feature the 'Bazaar' brand name. 

Bazaar.com conducted an experiment involving a paid campaign with branded keywords, specifically those containing the word 'Bazaar'. The aim was to estimate the number of customers visiting their website through both sponsored and organic advertisement links. However, during week 10 of the Google campaign, a technical glitch occurred, preventing the capture of customer traffic data through sponsored advertisements. As a result, the team used data from weeks 1 to 9 to calculate the ROI for the sponsored ads.


Regarding the traffic data from Google and Bing, Bob, a member of Bazaar's marketing analytics team, calculated a 320% Return on Investment (ROI) on the company's expenditure for sponsored ads. However, there is skepticism surrounding his result. The main concern arises from the fact that individuals searching with the term 'Bazaar' are likely already inclined to visit Bazaar.com. This casts doubt on the actual effectiveness of the branded keyword ads. 


However, Myra, one of the executives, raised concerns about potential overestimation in the ROI calculations. She posited that customers already searching for 'Bazaar' were naturally inclined to visit their website, regardless of whether they were exposed to sponsored ads or not. In her view, these customers would likely find their way to the site via organic links even in the absence of sponsored ads. This led to a decision to analyze the campaign data to assess the real impact of sponsored ads on web traffic. They planned to compare the total web traffic from both sponsored and organic advertisements before and after the week 10 glitch — essentially, up to week 9 and the subsequent period.

The primary objective now is to decipher the true causal effect of these search ads on business outcomes. To achieve a comprehensive understanding, we will conduct an in-depth analysis by addressing the following key questions:



1. What's wrong with Bob’s ROI analysis?
2. What is the treatment and control of the experiment?
3. Is the First Difference reliable to estimate the causal effect of the treatment? 
4. How should we compare with Difference-in-Difference estimation or Pre-Post estimation?  
5. Based on our new treatment effect, what should be the corrected ROI? How is it compared with Bob’s ROI?



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




# Define the Treatment and Control
As per this experiment, stoppage of sponsored ads serves as a way to test the causality, hence in our analysis (say in difference in differences we would be testing difference of change in Google click through ads vs other platforms ) Google would serve as treatment
group (as there was impact of outage here) and Bing , yahoo and ask would serve as control groups (as there was no impact of outage) 

# Consider a First Difference Estimate

In our analytical approach, we focus on determining whether there's a significant change in total web traffic following the ad outage compared to the period before the outage. This comparison of pre- and post-outage data is crucial for gaining insights into the causal impact of the outage on website traffic. Given that the data is heavily skewed — with 75% of the data showing fewer than 10,000 clicks — we employ a log transformation. This transformation is a standard technique to normalize data, making it more suitable for model building. By using a log transform, we can mitigate the effects of the skewness in the data, leading to more reliable and interpretable analytical results

```{r}
# Try a simple pre-post estimator
# Simple pre-post estimator
google_data<- data %>% filter(platform == "goog")
model <- lm(log(total_traffic) ~ after, data = google_data)
summary(model)
```

### Interpretation:
The p-value of 0.998 suggests no significant insights from our test. While there appears to be a 13.06% increase in web traffic from Google, the high p-value indicates this is not statistically significant. Our current analysis, based on pre-post comparison within the treatment group, assumes constant market conditions, which might not hold true in scenarios like holiday seasons. To overcome these limitations, we propose using the Difference in Difference (DiD) method. DiD considers both treatment and control groups, offering a more reliable approach by accounting for external variations.


# Calculate the Difference-in-Differences

Prior to conducting a Difference-in-Differences analysis, it's crucial to verify the existence of parallel trends beforehand. This step ensures that the differences we're comparing are, in fact, meaningful. If there's already a decreasing trend between the differences, it would hinder our ability to derive accurate insights.   

### Visualization of parallel trend
```{r,fig.show = "hold", out.width = "60%"}
temp1 = data %>%  filter(platform %in%  c('bing')) %>% select(week, total_traffic)
temp2 = data %>%  filter(platform %in%  c('yahoo')) %>% select(week, total_traffic)
temp3 = data %>%  filter(platform %in%  c('ask')) %>% select(week, total_traffic)

ggplot(data %>% filter(platform == 'goog'), aes(x=week, y= total_traffic, color = 'Google')) +
  geom_line() +
  geom_line(aes(x=week, y= total_traffic, color = 'Bing'), data = temp1) +
  geom_line(aes(x=week, y= total_traffic, color = 'Yahoo'), data = temp2) +
  geom_line(aes(x=week, y= total_traffic, color = 'Ask'), data = temp3) +
  geom_vline(xintercept = 9,color='red') +
  scale_y_continuous(sec.axis = sec_axis(~./6)) +
  scale_x_continuous(breaks = seq(1, 12, by = 1)) +
  labs(y = "Total Traffic", x = "Week") +
  theme_bw() +
  theme(legend.title = element_blank())
```

<img width="732" alt="Screenshot 2024-01-25 at 22 57 32" src="https://github.com/trungle14/trungle14.github.io/assets/143222481/e5a2d414-9a27-45c6-8f93-6ba7a7b9fab7">

The graph shows no parallel trends, but rather an increasing divergence until week 9, followed by a decrease in Google's click-through numbers compared to other platforms, indicating convergence. Therefore, while DiD analysis remains valuable, it requires cautious application and careful interpretation of the results.


```{r}
model_did <- lm(total_traffic ~ treatment + factor(week) + treatment * factor(week),data=data)
summary(model_did)
```

Although our initial assumption was not confirmed, we proceeded with a Difference in Difference (DiD) regression between the treatment and control groups. This approach aims to estimate the actual causal impact of the sponsored ads. The key independent variables in the DiD regression are Treatment, After, and the Interaction between Treatment and After.

```{r}
did <- lm(total_traffic ~ treatment + after + treatment * after, data=data)
summary(did)
```

By stopping sponsored ads on Google, Bazaar experiences an average loss of 9,910 clicks per week. This finding, derived from comparing the new treatment effect with the control group, highlights the causal influence of sponsored ads. This method is superior to the pre-post estimate because it allows us to analyze the behaviors of both control and treatment groups in a single model, adjusting for time-related variations and minimizing the impact of seasonality


