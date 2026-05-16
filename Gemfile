# =============================================================================
# CareCircle legal site — Gemfile.
#
# Only used for *local* preview (`bundle exec jekyll serve`). GitHub Pages
# itself builds the site server-side with its own pinned versions and does
# not read this file.
# =============================================================================
source "https://rubygems.org"

# Pinned to the version GitHub Pages currently runs. See:
#   https://pages.github.com/versions/
gem "github-pages", "~> 232", group: :jekyll_plugins

# Required for newer Ruby versions where webrick isn't bundled by default.
gem "webrick", "~> 1.8"

# Performance niceties for local builds; safely ignored by GitHub Pages.
gem "wdm", "~> 0.1.1", platforms: [:mingw, :x64_mingw, :mswin]
gem "tzinfo-data", platforms: [:mingw, :x64_mingw, :mswin, :jruby]
