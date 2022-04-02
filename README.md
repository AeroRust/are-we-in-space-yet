# are-we-in-space-yet [![Build Status](https://travis-ci.org/AeroRust/are-we-in-space-yet.svg?branch=master)](https://travis-ci.org/AeroRust/are-we-in-space-yet)

**Rust is a systems programming language that can work very well in hardware constrained environments. But is it running is space?**

[www.areweinspaceyet.org](http://www.areweinspaceyet.org)

Inspired by [Are We Learning Yet?](http://arewelearningyet.com/), this project aims to catalog rust usage in the aerospace industry.

## Contributing

Feedback, issues, and pull requests are welcome and appreciated for adding missing crates,
providing additional resources, or more generally improving the content.

## Running locally

Running locally is just a matter of installing jekyll and serving the site:

```
bundle install

# GitHub OAuth token avoids 403 rate limiting errors while generated crate data
export GITHUB_OAUTH_TOKEN=<YOUR_GITHUB_TOKEN>

# GitLab OAuth token Gives you access to more data, notably open issues count
# see https://docs.gitlab.com/ee/api/#authentication
export GITLAB_TOKEN=<YOUR_GITLAB_TOKEN>

bundle exec jekyll serve
```

The site should be running on [localhost:4000](http://localhost:4000)

## Generating crate data

`_data/crates.yaml` contains a manually curated list of crates,
but the `crate_gen.rb` plugin will fetch additional data from crates.io
and the GitHub API. All fetched and generated data is cached
to speed up site generation and avoid hammerring APIs.

To force regeneration of all data, remove all cached data with `rake clean`.
