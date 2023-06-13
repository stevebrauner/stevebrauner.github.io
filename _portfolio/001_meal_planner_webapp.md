---
layout: single
title: "Meal Planner Webapp"
excerpt: "A Django based webapp."
classes: wide
header:
  teaser: /assets/images/mp_index.png
feature_row:
  - image_path: /assets/images/mp_index.png
    alt: "Meal Planner WebApp index page."
    excerpt: "index page -- [view](/assets/images/mp_index.png)"
  - image_path: /assets/images/mp_plans.png
    alt: "Meal Planner WebApp plans page."
    excerpt: "plans page -- [view](/assets/images/mp_plans.png)"
  - image_path: /assets/images/mp_plan_detail.png
    alt: "Meal Planner WebApp plan detail page."
    excerpt: "plan details page -- [view](/assets/images/mp_plan_detail.png)"
  - image_path: /assets/images/mp_edit_plan.png
    alt: "Meal Planner WebApp plan edit page."
    excerpt: "plan edit page -- [view](/assets/images/mp_edit_plan.png)"
  - image_path: /assets/images/mp_register.png
    alt: "Meal Planner WebApp registration page."
    excerpt: "registration page -- [view](/assets/images/mp_register.png)"
---

# Meal Planner: A django based webapp

{% include feature_row %}

This is a Django based app that allows users to plan their meals.

As stated on the home page: Plan your meals. Planning meals has never been easier. Add plans by date for breakfast, lunch, dinner, and even a snack.

## Design Specification

Users will be able to plan their meals.

For user authentication users will need to be able to register, log in, log out, and
delete their account.

Users will need to be able to create, view, edit, and delete plans (based by date)
for breakfast, lunch, dinner, and other meals.

The home page will describe the app and will invite users to register or log in. After
logging in it will display the username welcome and ability to log out.

## Technical Specification

The database will need to track plans by owner (user).

Each plan will have breakfast, lunch, dinner, and other meals.

Each meal will have a title/description.

## Coding Reflections

- Used previous knowledge of coding a Django app to create this meal planner.
- Created a Project Specification to plan the project and keep on track with coding the various features.
- Provided users the ability to create and delete their user accounts.
- Used BootStrap 5 to create consistent look and feel.
- Added JQuery functioning for date pickers.

## Source Code and Demo

View code in the repo on <a href="https://github.com/stevebrauner/meal_planner">GitHub</a>.

View <a href="https://stevebrauner.pythonanywhere.com">demo here</a>.
