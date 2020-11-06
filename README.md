# bags

AH! I finally figured out how to test and build this website. Summary:

(1) Install [bundle](https://bundler.io/). This means:

```
gem install bundler
```

This will create a `Gemfile` file locally.

(2) Make sure that `Gemfile` includes BOTH jekyll AND the jekyll theme. I just
chose a random theme here, *but I'm not actually using it at all --- it's just
plain html*. The theme must be something unique to GitHub pages and is
necessary to get anything to work. For reference, here's what the `Gemfile`
has:

```
# frozen_string_literal: true

source "https://rubygems.org"

git_source(:github) {|repo_name| "https://github.com/#{repo_name}" }

# gem "rails"

gem "jekyll-theme-cayman"
gem "jekyll", "3.9.0"
```

I set this to be Jekyll version 3.9.0 following the GitHub pages documentation,
since it lists that as the current version.

(3) The `_config.yml` file must also have the correct jekyll theme.

```
theme: jekyll-theme-cayman
```

I actually did this via the point-and-click GUI interface on GitHub. It
automatically created `_config.yml` for me.

(4) Install bundle and the required "gems" from the specified sources:

```
bundle install
git add Gemfile Gemfile.lock
```

If I make further changes to `Gemfile`, then keep updating it with `bundle
install`. ([Here's a helpful StackOverflow
answer](https://stackoverflow.com/questions/46380722/jekyll-theme-could-not-be-found).)
This should also automatically create the `Gemfile.lock` method. Make sure both
are added to GitHub.

(5) Test and update locally with:

```
bundle exec jekyll serve
```
