# Lighthouse Average Performance

Lighthouse is an amazing tool to audit your app for performance, accessibility,
progressive web apps, SEO and more. Overral, it works pretty well, but when it
comes to assessing the performance of an app, there is an inherent variability
factor we should expect.

On its [_Lighthouse Metric Variability and
Accuracy_](https://docs.google.com/document/d/1BqtL-nG53rxWOI5RO0pItSRPowZVnYJ_gBEQCJ5EeUE/edit#),
the Lighthouse team describes this problem in more depth, explaining the
sources, the impact and how can it be mitigated.

This repository intends to mitigate the variability factor by consecutively
running the lighthouse performance audit n-times and averaging the results on
the created reports.

## How to use it

The project consists of two Node JS scripts (`generate-reports.js` and
`parse-reports.js`). To use them, you need Node 10+. The `generate-reports` will
run the lighthouse script _n-times_ and put the reports on a directory. The
`parse-reports` will read the reports generated by the former script on a
certain directory and generate the average performance metrics.

At the top of each script, there are variables you should customize to use them.
To run the scripts, you can do:

```sh
APP_URL="my-custom-url" ./generate-reports.js
APP_URL="my-custom-url" ./parse-reports.js
```

## Useful Links

- [Lighthouse Report Viewer](https://googlechrome.github.io/lighthouse/viewer/),
  drop a json report and see it in a more human-readable format.
- [Lighthouse Metric Variability and
  Accuracy](https://docs.google.com/document/d/1BqtL-nG53rxWOI5RO0pItSRPowZVnYJ_gBEQCJ5EeUE/edit?usp=sharing)
- [The Magic of Running Multiple Lighthouse Performance Tests on
  macOS](https://medium.com/@iamasamanthaa/the-magic-of-running-multiple-lighthouse-performance-tests-on-macos-4d22ae56621c),
  the first script was based on this article.
