# frozen_string_literal: true

source "https://rubygems.org"

gem "jekyll-theme-chirpy"

gem "html-proofer", "~> 5.0", group: :test

platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

#gem "wdm", "~> 0.1.1", :platforms => [:mingw, :x64_mingw, :mswin]

gem "webrick", "~> 1.9"
gem 'jekyll-compose', group: [:jekyll_plugins]
gem 'wdm', '>= 0.1.0' if Gem.win_platform?
gem 'jekyll-sitemap'
