# utspeech.github.io

## Posting a new meeting

First, copy this into a file under directory `data/meetings` with a name ending
in `.yaml` (e.g. `<lastname>-<year>.yaml`), then fill it out appropriately.

``` yaml
speaker: Parachute Pants  # name of speaker
website: https://www.google.com  # speaker's webpage (if available)
date: 2002-01-01  # date of presentation (YYYY-MM-DD)
time: 10:30  # time of presentation (24-hr)
affiliation: Your mom  # speaker's provided affiliation
title: "Mirror eyes"  # title of talk (use quotations if the title contains a colon)
zoom: https://www.bing.com  # zoom link
archive: https://www.duckduckgo.com  # archive link (if different from zoom link)
abstract: >
  The multiline extended abstract goes 
  right here
```

This will update the archive automatically. To post the announcement on the
main page, assuming the file was named `pants-2002.yaml' run from the terminal

``` sh
hugo new posts/pants-2002.md
```

and review the generated file. If you see no errors, set

``` yaml
draft: false
```

and push the site. Don't forget to also post the content to listserv.
