# Website Smoke Test

Using wget to clone a hosted website locally, once it has been brought down, run [HTML-Proofer](https://github.com/gjtorikian/html-proofer) to verify links, imgs, favicons, scripts, and optionally HTML markup. This is very handy to quickly check any production site for errors, it will only currently focus on a particular domain (if you need more I recommend using the underlying tool html-proofer.

## Requirements

* ruby
* wget ( brew install wget )

## Install

1. Clone this repo
2. ```bundle install```
4. ```URL="https://www.framebridge.com" bundle exec rake ```

## TODO

1. Parallelize download of site. ASAP
