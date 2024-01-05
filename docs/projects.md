---
layout: page
title: Projects
permalink: /projects/
---
## Table of Contents
- Less "Techy" Projects
	- [Serene Jewellers](#serene-jewellers)
	- [Excel Experts](#excel-experts)
- More "Techy" Projects
	- [Local Web Server](#local-web-server)

## [Serene Jewellers](https://serenejewellers.com/)

![Serene Jewellers Home](/assets/images/sj_home.png)

**Description:** A Toronto based, made to order, online Jewellery shop.
**Tech Stack**: Shopify
**My Experience:** Many CS majors can relate when asked by friends and family, "Hey, can you build *x* for me?". I was asked to help build a Shopify store, and I thought it could be an interesting project since it would require some technical and product knowledge. Specifically, I was interested in Shopify's provided user metric dashboards, and once traffic begins to pick up I would love to make improvements to conversion and returning customer numbers.
**Highlights:**
- I communicated often with the business owner; gathering requirements, explaining certain design decisions, and giving general advice on user flow. 
- I recommended and implemented certain engagement features, such as one time discount for providing email and building bundles.
- Wrote custom Liquid code for product pages that filters product images based on the selected variant.

![Serene Jewellers Product](/assets/images/sj_product.png)

**Concluding Remarks:** The current traffic is purely organic as marketing has not started, so I am pretty hands off on this project at the moment. Happy to report that we've made over $2,000 in sales so far!
## [Excel Experts]() (Site Under Construction)

![Excel Experts Home](/assets/images/ee_home.png)

**Description:** Excel consultancy.
**Tech Stack**: WordPress, hosted on Blue Host
**My Experience:** My motivation for this project is for me to be able to provide my friends to monetize their skills and a platform to engage with customers. I wanted to have a more direct role in the product, compared to Serene Jewellers, so I became a co-founder. I will be responsible for growth, UX, and tech.
**Highlights:**
- I created a business plan based on what we can offer and taking inspiration from competitors.
- Cleaned up UI to reflect the essential components of the UX that will increase conversion.
- Handled every component from setting up web host to writing all the text on the website.
**Conclusion:** The transferable skills are quite nice and I hope to follow these steps to create more businesses with others. There is still some work that needs to be done before the site goes live.

## [Local Web Server]() (WIP)

**Description:** HTTP Server.
**Tech Stack**: Written in C, hosted on my Pi running Arch Linux.
**My Experience:** This is a very fun project for me, since I've always wanted to combine my low level programming knowledge with a real world application. This started off as a simple handling of HTPP requests, however I am currently adding threading support with *my own* threading library - I am not using Pthreads.
**Highlights:**
- HTTP request parser
- New thread for each a new connection
	- Round robin thread scheduling
	- Zombie thread cleanup
- LRU Caching using simplified 2Q Algorithm