source "https://rubygems.org"

# management of Jekyll dependencies for github pages
require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)
gem 'github-pages', versions['github-pages']
gem 'redcarpet'
