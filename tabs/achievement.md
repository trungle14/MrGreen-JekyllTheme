---
layout: links
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_links

# publish date (used for seo)
# if not specified, site.time will be used.
#date: 2022-03-03 12:32:00 +0000

# for override items in _data/lang/[language].yml
#title: My title
#button_name: "My button"
# for override side_and_top_nav_buttons in _data/conf/main.yml
#icon: "fa fa-bath"

# seo
# if not specified, date will be used.
#meta_modify_date: 2022-03-03 12:32:00 +0000
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# if you enabled image_viewer_posts you don't need to enable this. This is only if image_viewer_posts = false
#image_viewer_on: true
# if you enabled image_lazy_loader_posts you don't need to enable this. This is only if image_lazy_loader_posts = false
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false


# you can always move this content to _data/content/ folder
# just create new file at _data/content/links/[language].yml and move content below.
###########################################################
#                Links Page Data
###########################################################
page_data:
  main:
    header: "Achievement 🥇"
    info: " "

  # To change order of the Categories, simply change order. (you don't need to change list order.)
  category:
    - title: "Educations"
      type: id_educations
      color: "gray"

    - title: "Awards"
      type: id_experience
      color: "#F4A273"

    - title: "Professional Journey"
      type: id_Skills
      color: "#62b462"

    - title: "Publication"
      type: id_projects
      color: "#F4A273"
      
  list:
    # id_educations
    - type: id_educations
      title: "Bachelor of Science in Finance Banking"
      # url: "https://garmsar.iau.ir"
      info:  "Banking University of Ho Chi Minh City 
      <br><i>Top 1% of High-Quality Program</i>
  <b style=\"float: right;\">2014-2018</b>"

    - type: id_educations
      title: "Master of Science in Business Analytics"
      # url: "https://garmsar.iau.ir"
      info:  "Carlson School of Management - University of Minnesota <br><i>GPA: 3.7</i> <b style=\"float: right;\">2023-2024</b>"

    # Experience

    - type: id_experience
      title: "Champion of Talent Generation Contest"
      info:  "National contest with the consecutive challenges as
      Academic knowledge, English ability, IQ & EQ, Numerical and Verbal reasoning test and business
      case with topic: “How Apple Pay enter Vietnamese market in 2019?”.
      Won the visiting trip to Google, Facebook, Amazon and NUS in Singapore <b style=\"float: right;\">2018</b>"

    - type: id_experience
      title: "1st Prize in National Olympic Contest of Econometrics and Applications" 
      info:  "Awarded the 1st prize by Central Vietnam Student Association with the research of 'Determinants of the possibilities by investors’ risk-taking: Empirical evidence from Vietnam' among 100+ research reports from 28 universities and institutes in Vietnam. In those reports, only the best 8 ones were chosen to report on the           final round. The goal of this competition is also to concentrate on developing mathematical, statistical, and econometric models that could be applied to solve practical problems in Economics, Finance, and Administration.  <b style=\"float: right;\">2017</b>"



    - type: id_Skills
      title: "FE CREDIT (Vietnam Prosperity Bank – Sumitomo Mitsui Corporation)"
      info: "Head of Portfolio Analytics & Management | Risk Management <b style=\"float: right;\">2022-2023</b><br>
      Portfolio Analytics Manager | Risk Management<b style=\"float: right;\">2020-2022</b><br>
      Management Associate | Collections | Risk Modeling | Business Intelligence |<b style=\"float: right;\">2018-2020</b>"

      
    - type: id_Skills
      title: "PriceWaterhouse<br>Coopers(PwC"
      info:  "Financial Audit Intern <b style=\"float: right;\">2017-2018</b>"




      
    # id_projects:
    - type: id_projects
      title: "DETERMINANTS IMPACTING THE POSSIBILITIES OF INVESTORS’ RISK-TAKING: EMPIRICAL EVIDENCE FROM VIETNAM (click here)"
      url: "https://www.tandfonline.com/doi/full/10.1080/23322039.2021.1917106/"
      info: "Determinants of the possibilities by investors’ risk-taking: Empirical evidence from Vietnam, Cogent Economics & Finance, 9:1, DOI: 10.1080/23322039.2021.1917106 <i><a href='https://www.tandfonline.com/doi/full/10.1080/23322039.2021.1917106/'>here</a></i>"




---
