---
layout: single
title: "witnesstowisdom.com Website"
excerpt: "A blogging website."
classes: wide
header:
  teaser: /assets/images/witnesstowisdom.png
feature_row:
  - image_path: /assets/images/witnesstowisdom.png
    alt: "witnesstowisdom.com index page."
    excerpt: "index page -- [view live site](https://witnesstowisdom.com)"
---

# witnesstowisdom.com: A blogging website

{% include feature_row %}

This is a Django based website focused on blogging. It is expandable to include a membership site, products, etc.

## Welcome to Witness to Wisdom

_Witnessing to wisdom for the spiritually independent._

There is a wisdom that runs through many traditions that speaks to the core of who we feel we really are.

This is a website where we witness to this wisdom, and talk about what it might mean in our daily lives.

**Witness to Wisdom** offers resources to enrich our journeys for living a deep and rich spiritual life:

- weekly blog posts with reflections on this wisdom lived in our daily lives
- newsletters sent weekly to your inbox so you don't miss a thing

## Design Specification

- The Website will be written in Python and the Django framework.

- There will be static pages for Home, About, and Contact Us.

- The Blog will have categories, tags, and comments.

- There will be a newsletter signup form.

## Technical Specification

- The website will have its own domain name.

- The repo will live at GitHub and will be private for security.

- The Python version will be the newest stable version.

- Django and modules will be kept up to date.

- The database will be PostgreSQL.

- The site will be deployed in a Docker container.

- The site will be deployed via aws with ssl certificate.

## Coding Reflections

- The database is on AWS RDS.

- The ssl certificates are managed with Let's Encrypt in a Nginx Proxy container.

- Initial deployment was on fly.io and later converted to AWS S3 bucket with Cloudfront access.

## Update

I found that the cost of deploying this on AWS was beyond my budget. I have since redeployed this site as a Jekyll based static site on AWS which no longer needs the extra cost of the database. A contact form is deployed with a AWS Lambda function.

## Django Based Source Code

The Django based code is now public and hosted on GitHub at [https://github.com/stevebrauner/witnesstowisdom](https://github.com/stevebrauner/witnesstowisdom)

## Jekyll Based Source Code and Live Site

The code repo for the Jekyll based site is hosted on GitHub at [https://github.com/stevebrauner/witnesstowisdom-static](https://github.com/stevebrauner/witnesstowisdom-static). The live site is at [https://witnesstowisdom.com](https://witnesstowisdom.com).
