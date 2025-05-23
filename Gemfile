source "https://rubygems.org"

gem "jekyll", "~> 4.4.1"
gem "just-the-docs", "~> 0.10.1"
gem "csv"
gem "logger"
gem "base64"

group :jekyll_plugins do
  gem "jekyll-remote-theme"
  gem "jekyll-include-cache"
end

# Windows and JRuby does not include zoneinfo files
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

gem "webrick", "~> 1.8"