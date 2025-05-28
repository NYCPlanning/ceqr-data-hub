# ceqr-data-hub

The CEQR Data Hub website is powered by this repository, which uses GitHub Pages and a custom theme. It is maintained by the NYC Department of City Planning’s Data Engineering team.

## Development

These instructions are for macOS or Linux.

The latest 3.3 version of ruby is used to align with the github action used to build the site.

### Setup

1. Install rbenv with Homebrew using `brew install rbenv`
2. Set up your shell to load rbenv using `rbenv init`
3. Find the latest version of ruby 3.3 using `rbenv list -l`
4. Install latest 3.3 version using `rbenv install 3.3.x` (replace the `x` to reflect the installed version)
5. Set this version as the new default using `rbenv global 3.3.x`
6. Verify the default ruby version using `ruby -v`
7. Run `bundle install` from the root directory of this repo (may eliminate need to run `gem install github-pages`?)

### Run site locally

1. Start the local server using `bundle exec jekyll serve`
2. Navigate to `http://localhost:4000` or the the server address listed in the terminal

### Resources

[Markdown - Github Docs](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github)

[Minimal theme for GitHub Pages](https://github.com/pages-themes/minimal)

[Testing your GitHub Pages site locally - GitHub Docs](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll)

[jekyll-build-pages Github action repo](https://github.com/actions/jekyll-build-pages)
