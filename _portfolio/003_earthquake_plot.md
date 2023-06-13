---
layout: single
title: "Earthquake Plotting CLI"
excerpt: "An earthquake plotting CLI app."
classes: wide
header:
  teaser: /assets/images/earthquake_cli.png
feature_row:
  - image_path: /assets/images/earthquake_cli.png
    alt: "Earthquake Plotting CLI app"
    excerpt: "CLI in use -- [view](/assets/images/earthquake_cli.png)"
  - image_path: /assets/images/earthquake_plot.png
    alt: "Earthquake Plot display"
    excerpt: "Earthquake plot display -- [view](/assets/images/earthquake_plot.png)"
---

# Earthquake Plotting CLI App

{% include feature_row %}

- Uses data from USGA for magnitude 1 or greater earthquakes in the last day, week, or month.
- The CLI uses the click library.
- CLI has commands to update the data/plots, and display plots in the default browser.

## Coding Reflections

- This project was inspired from a project in *Python Crash Course, 2nd Edition* by Eric Matthes.
- Implemented fetching of data from USGA site (original project had static files for data).
- Attempted to implement as a GUI but was unable to get plots to render properly with interactive abilities.
- Created a CLI interface using the default browser for displaying the plots.
- Implementing this with a model will allow future upgrade to a GUI based MVC design.

## Source Code
See source code at the repo on <a href="https://github.com/stevebrauner/earthquake">GitHub</a>.
