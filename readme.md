# Website Smoke Test

Using wget to clone a hosted website locally, once it has been brought down, run [HTML-Proofer](https://github.com/gjtorikian/html-proofer) to verify links, imgs, favicons, scripts, and optionally HTML markup.

**Currently hits https://www.theironyard.com**

## Requirements

* ruby
* wget ( brew install wget )

## Install

1. Clone this repo
2. ```bundle install```
3. ```rake```
4. ```rake test``` # run tests without redownloading site

## TODO

1. Parallelize download of site. ASAP
2. Extract to be a thing, args for url / domain
