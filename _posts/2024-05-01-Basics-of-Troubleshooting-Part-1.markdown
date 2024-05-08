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

It's 4:55 PM on a Friday afternoon, you head out of the office and are on the freeway.
You're on call, and your phone rings. The automated system asks you to press 1 to receive a message. Production is down.
You throw your phone on the seat, and quietly rage.  You turn around and head back in the office.

Production is down, anyone trying to access the site is given a 50x. This is where the investigation begins

#### Understanding the issue
When a web server is displaying a 50x problem, it indicates a problem with the application. The first step you should
do if you're anything like me is to breathe, unless this is an extended outage, you will have time to investigate. Many times
people will hound you and continually ask for a status. Give them a short answer and continue to investigate. Don't let outside
stress get the best of you, it only drags out the process of troubleshooting and implementing a fix.

Always review logs, I cannot stress this enough. They usually give helpful information on what could be the cause of 
a problem. Try to watch the log in real time while reproducing the issue. In Linux you can use tail -f *.log and in Windows
you can fire up powershell and run Get-Content logfile.log -Wait. You will be able to see your request in the application
log and what error you get. 

Is it complaining about the database? Or is it a code issue? Were there any deployments that 
were done at the worst possible time, such as Friday right before the weekend? Understanding the circumstances can help you narrow down the problem.

A code deployment can break in the worst way. If a deployment did happen and things went awry you can lean towards
a problem with the deployment. Don't jump to a conclusion, just keep it in your file as you continue to troubleshoot.

### Gathering information
Investigating the log, you see an error. It is a stacktrace and it seems to be complaining about the database. Good,
you know that there's a problem with the application and the database. The exception seems to indicate a missing field
in the database that the application is looking for. It's time to find your nearest application developer and bring him
on the call. Application deployments sometimes require database migrations and if a field was missed or the database wasn't migrated
you can run into an issue like the one above.

### Sharing information
When you do find a problem in the log, determine if it's in your domain or if it's another teams issue. If it's a stack
trace that indicates a problem with the application, the applicable developer should be consulted. 

Do not play the blame game, instead keep the problem as blameless as possible, don't point fingers as you will do everyone a disservice. Instead, be diplomatic and remain calm.

### Troubleshooting Summary
The scenario follows these basic troubleshooting steps:
1. Identify the Problem:

    - Take the time to clearly understand what the issue is. Define it in specific terms and consider its impact on the system or process.
    - Avoid jumping to conclusions or making assumptions about the problem. Instead, focus on gathering facts and observations.

2. Gather Information:

    - Collect all relevant data and information related to the problem. This may include error messages, logs, recent changes, user reports, or any other relevant context.
    - Ensure you have a comprehensive understanding of the situation before proceeding to diagnose the problem.
