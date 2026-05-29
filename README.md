# ceqr-data-hub

The CEQR Data Hub website is powered by this repository, which uses GitHub Pages and a custom theme. It is maintained by the NYC Department of City Planning’s Data Engineering team.

## Development

These instructions are for macOS or Linux.

The latest 3.3 version of ruby is used to align with the github action used to build the site.

### Updating content

The markdown tables in [`pages/datasets.md`](pages/datasets.md) and [`pages/chapters.md`](pages/chapters.md) are **generated** — do not edit them directly. Changes will be overwritten the next time the build runs.

The source of truth lives in the [`data-engineering`](https://github.com/NYCPlanning/data-engineering) repo under `products/ceqr/seeds/`:

- **`datasets.csv`** — one row per dataset: name, download key, file type, source URL
- **`chapter_datasets.csv`** — which datasets appear in which chapters and their use descriptions

To update content:

1. Edit the relevant seed CSV(s) in `data-engineering`
2. Run the CEQR Build GitHub Action in the `data-engineering` repo
3. Download `datasets_table.md` and `chapters_tables.md` from `edm-publishing/db-ceqr/build/<branch-name>/` in Digital Ocean
4. Copy them to `pages/datasets.md` and `pages/chapters.md` in this repo

### Updating data

Dataset files served by the download links are stored in the `ceqr-data-hub` Digital Ocean Space under `latest/`. To update them:

1. Run the CEQR Build GitHub Action in the `data-engineering` repo
2. Copy the dataset files from `edm-publishing/db-ceqr/build/<branch-name>/` to `ceqr-data-hub/latest/`

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
