run: `bundle exec jekyll serve`

theme: https://github.com/riggraz/no-style-please

## mise

1. `brew install libyaml` (required because mise will build Ruby from source)
2. `mise exec ruby@3.4 -- bundle install`
3. `mise exec ruby@3.4 -- bundle exec jekyll serve`
