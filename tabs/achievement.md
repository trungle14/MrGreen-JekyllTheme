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
      title: "1st Prize in National Olympic Econometrics and Applications Contest" 
      info:  "Carlson School of Management - University of Minnesota <b style=\"float: right;\">2017</b>"

    - type: id_experience
      title: "<a href=https://dkap.ir/>DKApadana</a>"
      info:  "<b>C/C++ Programmer</b> <b style=\"float: right;\">2021-2021</b><br></br>Throughout the course of my time in this company I did the development of Android apps using Linux. Moreover, <b>C++11 </b> with <b>Felgo</b> Framework were among the commonly used technologies."

    - type: id_experience
      title: "<a href=https://hanasystemsco.com/>HANA</a>"
      info:  "<b>C/C++ Developer, DB Designer and SysAdmin</b> <b style=\"float: right;\">2019-2021</b><br><br/<b>Linux</b> and <b>Windows</b> development for Management UAV(Drone) Use-cases with the aid of <b>C++11</b>, <b>Qt</b>, <b>QML</b>, various <b>Database</b> technologies"

    - type: id_Skills
      title: "C/C++"
      info:  "<i>Proficient in:</i> Standard <b>Standard C++1, Qt, Felgo Framework with the usage of QML in order to develop User Interface, and usage of IDF for firmware development.</b> <br> <i>Familiar with:</i> <b>Multi-threading under C++11 thread library</b>"

    - type: id_Skills
      title: "DB"
      info:  "<i>Experienced with:</i>Experienced with: Database design through hand-written queries."

    - type: id_Skills
      title: "GNU/Linux SysAdmin"
      info:  "<i>Experienced with:</i> IPtables , DNS , Docker, Podman , Hardening Linux"


      
    # id_projects:
    - type: id_projects
      title: "DETERMINANTS IMPACTING THE POSSIBILITIES OF INVESTORS’ RISK-TAKING: EMPIRICAL EVIDENCE FROM VIETNAM (clink here)"
      url: "https://www.tandfonline.com/doi/full/10.1080/23322039.2021.1917106/"
      info: "Determinants of the possibilities by investors’ risk-taking: Empirical evidence from Vietnam, Cogent Economics & Finance, 9:1, DOI: 10.1080/23322039.2021.1917106 <i><a href='https://www.tandfonline.com/doi/full/10.1080/23322039.2021.1917106/'>here</a></i>"




---
