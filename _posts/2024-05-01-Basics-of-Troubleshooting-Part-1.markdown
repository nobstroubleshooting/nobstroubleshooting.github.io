---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_tshoot_1
title: Basics of troubleshooting and soft skills part 1

# post specific
# if not specified, .name will be used from _data/owner/[language].yml

# multiple category is not supported
category: troubleshooting
# multiple tag entries are possible
tags: [troubleshooting, technique, production down, soft skills]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
#comments_disable: true

# publish date
date: 2024-05-06 08:11:06 -0400

# seo
# if not specified, date will be used.
#meta_modify_date: 2022-02-10 08:11:06 +0900
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
published: true
---
<!-- outline-start -->

A sample scenario that really did happen, an example of what could be wrong, and how to deal with people..

<!-- outline-end -->

### Identifing the problem

So, picture this: it’s almost 5 PM on a Friday, You're cruising down the freeway, all set for the weekend. Suddenly, your phone starts buzzing like crazy. An automated voice tells me to press 1 for a message. It’s bad news – production is down. Cue the internal frustration and a swift U-turn back to the office.

Yep, you guessed it. The site’s throwing a 50x error at anyone who dares to visit. And just like that, the weekend plans are on hold while we dive deep into the investigation.

#### Understanding the issue
You are confronted with a 50x error from your web server. It may initially incite panic. However, it's crucial to maintain composure. Take a moment to collect yourself; unless it's a dire situation, there's time to address the issue. Expect inquiries from concerned parties seeking updates; provide a brief status update and proceed with troubleshooting.

The cardinal rule in such scenarios is to review the logs. These logs serve as invaluable guides in navigating troubleshooting sessions. Utilize tools like the Linux terminal or Windows PowerShell to monitor logs in real-time. This enables quick identification of requests and any associated errors.

Subsequently, embark on a fact-finding mission. Determine whether the issue stems from database malfunctions, code discrepancies, or recent deployments. A nuanced understanding of the circumstances facilitates targeted problem-solving.

In the event of a deployment mishap, resist the urge to assign blame prematurely. Instead, maintain focus on resolution. Keep deployment-related factors in mind as you look deeper into the issue. Remember, there's often more to uncover in the intricate landscape of code troubleshooting.

### Gathering information
As you look into the logs, a glaring error catches your eye: a detailed stack trace hinting at a database issue. This discovery solidifies the understanding that both the application and the database are at the heart of the problem.

Specifically, the error message suggests a missing database field that the application is seeking. This realization prompts the next strategic move: enlist the expertise of an application developer.

In the realm of application deployments, database migrations often play a pivotal role. Oversights in migration processes, such as skipping essential fields, can readily lead to the sort of issue we're currently facing. It's imperative to collaborate with a developer to unravel this puzzle.

### Sharing information
Upon uncovering an issue within the logs, it's crucial to discern whether it falls within your realm of responsibility or if it pertains to another team's domain. Should the error manifest as a stack trace of an application malfunction, it's prudent to engage the relevant developer for consultation.

In addressing such challenges, it's imperative to avoid the temptation of assigning blame. Adopting a blameless approach not only fosters a collaborative environment but also prevents unnecessary friction. Instead, maintain a diplomatic demeanor and prioritize problem-solving with composure.

### Troubleshooting Summary
The scenario follows these basic troubleshooting steps:
1. Identify the Problem:

    - Take the time to clearly understand what the issue is. Define it in specific terms and consider its impact on the system or process.
    - Avoid jumping to conclusions or making assumptions about the problem. Instead, focus on gathering facts and observations.

2. Gather Information:

    - Collect all relevant data and information related to the problem. This may include error messages, logs, recent changes, user reports, or any other relevant context.
    - Ensure you have a comprehensive understanding of the situation before proceeding to diagnose the problem.
