# Personal site

The repo contains sources for personal site www.smith3v.com.

Hugo-based site with automatic deployment to S3-like service.

## Local development

### 1. Install Node dependencies

The active theme uses PostCSS via Hugo Pipes. Install dependencies first:

```bash
npm ci
```

### 2. Run with Hugo (extended)

The site is verified with Homebrew Hugo `v0.155.3+extended+withdeploy`.

```bash
hugo server --disableFastRender
```

Build:

```bash
hugo
```

### 3. Optional: initialize legacy submodules

Some old/alternative themes in `themes/` are still submodules. They are not required for the active site theme, but can be initialized if needed:

```bash
git submodule sync --recursive
git submodule update --init --recursive
```

## Theme workflow (git subtree)

`themes/adritian-free-hugo-theme` is managed as a subtree (not a submodule).

### One-time setup

```bash
git remote add adritian-theme git@github.com:smith3v/adritian-free-hugo-theme.git
```

If the remote already exists:

```bash
git remote set-url adritian-theme git@github.com:smith3v/adritian-free-hugo-theme.git
```

### Pull latest theme changes into this repo

```bash
git subtree pull --prefix=themes/adritian-free-hugo-theme adritian-theme main --squash
```

### Push local theme changes back to theme repo

Commit your changes in this repo first, then:

```bash
git subtree push --prefix=themes/adritian-free-hugo-theme adritian-theme main
```
