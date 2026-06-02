# adir1hugo

Personal website showcasing technology, life insights, and professional perspectives built with Hugo and the Blowfish v2 theme.

**Live Site**: https://adir1.com/  
**Content Archive**: 18+ years (2007-2026)

## Tech Stack

- **Hugo**: Static site generator (v0.87.0+)
- **Theme**: Blowfish v2
- **Module System**: Hugo Modules (Go-based)
- **Markdown**: Goldmark with HTML support

## Prerequisites

Before getting started, ensure you have the following installed on your Mac:

- **Hugo** (v0.87.0 or later)
- **Go** (v1.19 or later) - required for Hugo Modules

### Installing Prerequisites

```bash
# Install Hugo via Homebrew
brew install hugo

# Verify Hugo installation
hugo version

# Install Go via Homebrew (if not already installed)
brew install go

# Verify Go installation
go version
```

## Local Development

### Setup

1. Clone the repository and navigate to the project directory:
```bash
cd /Users/adir1/git/adir1hugo
```

2. Download and update module dependencies:
```bash
hugo mod get -u
```

### Running Locally

Start the development server with draft posts included:

```bash
hugo server -D
```

This will:
- Start a local server at `http://localhost:1313`
- Include draft posts in the output (useful for testing unpublished content)
- Live reload on file changes

**Variations**:
- `hugo server` - Run without drafts (production-like preview)
- `hugo server --buildDrafts --buildFuture` - Include drafts and future-dated posts
- `hugo server --port 8080` - Run on a different port if 1313 is busy

### Building for Production

Generate the static site output:

```bash
hugo
```

Output will be generated in the `public/` directory.

### Other Useful Commands

```bash
# Clean build (remove cache and rebuild)
rm -rf resources/_gen && hugo

# Update all modules to latest versions
hugo mod get -u

# Verify module structure
hugo mod graph

# Build with verbose output (helpful for debugging)
hugo -v

# Check for broken links and issues
hugo check

# List all available posts
hugo list all
```

## Content Structure

- **Posts**: Main blog articles in `content/posts/`
- **About**: Static page at `content/about/`
- **Life Snippets**: Additional content section at `content/life_snippets/`
- **Config**: Site configuration in `config/_default/`

## Deployment

The site is configured for static deployment. The `public/` directory contains all files ready for CDN hosting.

```bash
# Generate and verify production build
hugo && ls -la public/
```

## Resources

- [Hugo Documentation](https://gohugo.io/)
- [Blowfish Theme Documentation](https://blowfish.page/docs/)
- [Markdown Guide](https://www.markdownguide.org/)
