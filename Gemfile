source "https://rubygems.org"

# Gem Jekyll pour GitHub Pages
gem "github-pages", group: :jekyll_plugins

# Plugins Jekyll compatibles GitHub Pages
group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-sitemap"
  gem "jekyll-seo-tag"
  gem "jekyll-paginate"
end

# Windows et JRuby ne supportent pas toutes les gems
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", "~> 1.2"
  gem "tzinfo-data"
end

# Gem wdm pour Windows
gem "wdm", "~> 0.1.1", :platforms => [:mingw, :x64_mingw, :mswin]
