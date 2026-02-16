# Personal site

The repo contains sources for personal site www.smith3v.com.

Hugo-based site with automatic deployment to S3-like service.

## Local development

### 1. Initialize submodules

Themes are stored as git submodules, so start with:

```bash
git submodule sync --recursive
git submodule update --init --recursive
```

### 2. Install Node dependencies

This theme uses PostCSS via Hugo Pipes. Install dependencies first:

```bash
npm ci
```

### 3. Use Hugo v0.128.1

This site works with Hugo `v0.128.1` (extended). Newer Homebrew Hugo versions fail on removed legacy APIs (`resources.ToCSS` and `resources.PostCSS`) used by the theme.

You can test without changing your Homebrew-managed Hugo by downloading a separate binary and running it directly:

```bash
mkdir -p /tmp/hugo-0.128.1
cd /tmp/hugo-0.128.1
curl -fL -o hugo_extended_0.128.1_darwin-universal.tar.gz \
  https://github.com/gohugoio/hugo/releases/download/v0.128.1/hugo_extended_0.128.1_darwin-universal.tar.gz
tar -xzf hugo_extended_0.128.1_darwin-universal.tar.gz
./hugo version
```

Run the site:

```bash
/tmp/hugo-0.128.1/hugo server --disableFastRender
```

Build:

```bash
/tmp/hugo-0.128.1/hugo
```
