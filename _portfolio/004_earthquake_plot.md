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

# Earthquake Plotting CLI app

{% include feature_row %}

- Uses data from USGA for magnitude 1 or greater earthquakes in the last day, week, or month.
- The CLI uses the click library.
- CLI has the following commands:
  - update -- downloads the data from USGA, parses the data, and creates the plots (via plotly library).
  - display -- accepts user input of DAY, WEEK, or MONTH to display the appropriate plot (via default browser) or q to exit.

<p>See source code at the repo on <a href="https://github.com/stevebrauner/earthquake">GitHub</a>.</p>
