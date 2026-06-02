---
title: "adir1hugo - Tech Stack & Capabilities"
description: "Complete technical documentation and capabilities of the adir1hugo project"
---

# adir1hugo - Tech Stack & Capabilities

**Project**: Personal website showcasing technology, life insights, and professional perspectives  
**Framework**: Hugo with Blowfish v2 theme  
**Status**: Active with 18+ years of content archive  

---

## Core Tech Stack

| Component | Technology | Version | Purpose |
|-----------|-----------|---------|---------|
| **Static Site Generator** | Hugo | 0.87.0+ | Content compilation & site generation |
| **Theme** | Blowfish v2 | v2.100.0 | Modern, responsive design framework |
| **Module System** | Hugo Modules | - | Dependency management via Go modules |
| **Language** | Go | 1.19 | Theme module implementation |
| **Markdown Processor** | Goldmark | - | Markdown parsing with HTML support |
| **Source Control** | Git | - | Version control |

---

## Content Management

### Structure & Organization
- **Content Types**: Posts, About, Life Snippets
- **Main Sections**: `post`, `posts`
- **Taxonomies Enabled**:
  - Tags
  - Categories
  - Authors
  - Series

### Content Capabilities
- **Markdown Support**: Full Goldmark with unsafe HTML rendering
- **Frontmatter**: YAML/TOML metadata support
- **Media**:
  - Optimized image handling (centered anchoring)
  - Hero images for articles and lists
  - Featured/inline images with CSS styling
  - Featured image galleries
- **Date Management**: Automatic date sorting, custom date formats (e.g., "2 January 2006")
- **Drafts**: Support for draft posts with draft labels

---

## Display & Theme Features

### Appearance & Navigation
- **Color Scheme**: Forest (dark-first with light option)
- **Appearance Switching**: Auto-detection + manual toggle
- **Header**: Fixed layout with navigation
- **Footer**: Copyright, theme attribution, appearance switcher, scroll-to-top button

### Homepage Features
- **Layout**: Hero layout with featured image
- **Display Options**: 
  - Recent posts (configurable: 5 items shown)
  - "Show More" link to posts archive
  - Card-based view
  - Customizable background image

### Article Display Features
- **Reading Indicators**:
  - Reading time estimate
  - Word count
  - Publication date
  - Author attribution
- **Navigation**:
  - Breadcrumbs
  - Table of Contents (levels 2-4)
  - Heading anchors for direct linking
  - Previous/Next article pagination
- **Visual Styling**:
  - Hero images (background style)
  - Background blur effects
  - Heading anchor links
  - Draft labels on unpublished content
- **Engagement**:
  - Social sharing buttons (LinkedIn, Twitter, Reddit, Facebook, Email)
  - Author badges (optional)
  - Taxonomy display

### List & Archive Features
- **Grouping**: Posts grouped by year
- **Card View**: Visual card-based layout
- **Pagination**: 20 items per page
- **Summary Display**: Post summaries on list pages
- **Taxonomy Pages**: Category/tag/author pages with term counts

---

## Available Extensions & Features

### Shortcodes (Built-in Blowfish)
Blowfish includes a comprehensive set of shortcodes beyond the default Hugo shortcodes:

**Rich Content**:
- `alert` - Styled message boxes with custom icons and colors
- `admonition` - GitHub-style callout boxes (TIP, WARNING, NOTE, etc.)
- `lead` - Emphasized introduction text
- `badge` - Styled metadata badges
- `button` - Call-to-action buttons with internal/external links

**Media & Visualization**:
- `figure` - Enhanced image handling with optimization and captions
- `gallery` - Responsive multi-image gallery with grid layout
- `carousel` - Slideshow with auto-scroll and captions
- `video` - Embed local/external videos with playback controls
- `mermaid` - Diagrams and flowcharts (flowchart, sequence, Gantt, state, ER, class, git, pie)
- `katex` - Mathematical expressions with TeX syntax
- `chart` - Chart.js integration for data visualization

**Content Organization**:
- `accordion` - Collapsible panels with single/multiple open modes
- `tabs` - Tabbed content with synchronized groups
- `timeline` - Visual timeline for events/experiences
- `list` - Dynamic list of recent articles with filtering

**Code & Integration**:
- `codeimporter` - Import code from external URLs with line ranges
- `icon` - SVG icons from built-in or custom icon sets
- `keyword`/`keywordList` - Highlight professional skills/keywords

**External Services**:
- `github` - Real-time GitHub repository cards (stars, forks, language)
- `gitlab` - GitLab project cards with live stats
- `gitea`/`codeberg`/`forgejo` - Self-hosted Git service cards
- `huggingface` - Hugging Face model/dataset cards
- `gist` - Embed GitHub Gists
- `article` - Embed other articles inline
- `mdimporter` - Import external markdown files

**Media Embedding**:
- `youtubeLite` - Lightweight YouTube embeds with parameters
- `typeit` - Typewriter effect text animation

**Utilities**:
- `email` - Obfuscated mailto links
- `swatches` - Color palette display
- `ltr`/`rtl` - Directional content mixing for RTL languages

### Markdown Extensions

#### Code Highlighting
- **Processor**: Chroma (via Hugo)
- **Configuration**: No classes mode disabled (inline styles)
- **Support**: 100+ programming languages
- **Features**:
  - Code copy button (enabled)
  - Line numbers (configurable)
  - Syntax highlighting

#### HTML Support in Markdown
- **Unsafe Mode**: Enabled
- **Allows**: Direct HTML embedding in markdown for advanced layouts
- **Use Cases**: Custom styling, embedded media, complex layouts

### Diagramming & Visualization

#### Mermaid Diagrams (Built-in Shortcode)
- **Status**: **Ready to use** - Built-in `mermaid` shortcode
- **Capabilities**: Flowcharts, sequence diagrams, Gantt charts, state diagrams, entity relationship diagrams, class diagrams, Git graphs, pie charts, and more
- **Usage**: Use the `{{< mermaid >}}` shortcode in articles

**Example**:
```hugo
{{< mermaid >}}
graph LR
    A[Lemons] --> B[Lemonade]
    B --> C[Profit]
{{< /mermaid >}}
```

### Math & Scientific Notation

#### KaTeX Support (Built-in Shortcode)
- **Status**: **Ready to use** - Built-in `katex` shortcode
- **Format**: LaTeX/TeX syntax
- **Rendering**: Client-side via KaTeX.js
- **Support**: 1000+ TeX functions available
- **Usage**: Use the `{{< katex >}}` shortcode once per article

**Example**:
```hugo
{{< katex >}}
Inline: \(E = mc^2\)

Block: $$\int_0^\infty e^{-x^2} dx = \frac{\sqrt{\pi}}{2}$$
{{< /katex >}}
```

### Search Functionality
- **Status**: Enabled
- **Type**: Full-text search across content
- **Output**: JSON index generation (`index.json`)
- **Frontend**: Client-side search interface

---

## Analytics & Tracking

### Google Analytics
- **Tracking ID**: G-HDPJC6ZF5N
- **Status**: Configured and active
- **Data**: Page views, user engagement, traffic sources

### Optional Tracking Systems (Available but Disabled)
- **Firebase**: Authentication and analytics
- **Fathom Analytics**: Privacy-focused alternative
- **Verification**: Google, Bing, Pinterest, Yandex domain verification

---

## Content Features & Capabilities

### Article Features
- **Series Support**: Multi-part article series with auto-linking
- **Author Management**: Multiple authors per article, author pages
- **Category/Tag Management**: Hierarchical organization
- **Date Metadata**: Published date, updated date (optional display)
- **SEO**: Automatic sitemap generation, robots.txt
- **Social Features**: Sharing buttons on all articles

### Homepage Features
- **Recent Posts Display**: Latest 5 posts on homepage
- **Featured Images**: Hero images on homepage and articles
- **Navigation**: Quick links to posts archive and sections

### Multi-section Support
- **Posts**: Main blog content section (18+ years of archive)
- **About**: Static about page with author bio
- **Life Snippets**: Additional content section
- **Expandable**: Easy to add new content sections

---

## Configuration & Customization

### Logo & Branding
- **Author Name**: Adi Rabinovich
- **Author Image**: Profile picture support
- **Bio**: Author bio on profile/homepage
- **Social Links**: LinkedIn, GitHub, Mastodon, Instagram, Dev.to

### Site Configuration
- **Base URL**: https://adir1.com/
- **Language**: English (EN) with international support structure
- **Summary Length**: 30 characters (for previews)
- **Output Formats**: HTML, RSS, JSON

### Publishing Control
- **Build Drafts**: Disabled (drafts not published)
- **Future Posts**: Hidden until publication date
- **Pagination**: 20 items per page

---

## Recommended Extensions & Enhancements

### Quick Wins
1. **Custom Shortcodes**: Create project-specific shortcodes (e.g., tech-stack comparison, tool recommendation)
2. **Admonitions**: Use GitHub-style admonitions for better content organization
3. **Timeline/Tabs**: Leverage timeline and tabs shortcodes for more dynamic content

### Future Considerations
1. **Comments System**: Disqus or native alternative
2. **Related Posts**: AI-powered content recommendations (showRelatedContent config)
3. **Advanced Search**: Algolia integration for enhanced full-text search
4. **JSON-LD**: Structured data markup for better SEO
5. **Analytics Enhancement**: Switch from Google Analytics to privacy-focused Umami or Fathom

---

## Performance Characteristics

### Build & Deployment
- **Output**: Static HTML files (no server-side processing)
- **Build Time**: Fast (Hugo specializes in speed)
- **Deployment**: CDN-ready static files
- **Caching**: Browser caching + CDN edge caching support

### Image Optimization
- **Format**: Responsive image handling
- **Anchor**: Center-based image positioning
- **Optimization**: Hugo image processing pipeline

---

## Content Stats

- **Total Posts**: 1000+ articles
- **Date Range**: 2007-2026 (18+ years)
- **Sections**: 3 main content sections
- **Taxonomies**: 4 (tags, categories, authors, series)
- **Authors**: Multi-author capable
- **Categories**: Technology-focused with life/general topics

---

## File Structure

```
/
├── config/_default/          # Hugo configuration
│   ├── config.toml          # Main site config
│   ├── params.toml          # Theme parameters
│   ├── markup.toml          # Markdown/rendering config
│   ├── languages.en.toml    # i18n settings
│   ├── menus.en.toml        # Navigation menus
│   └── module.toml          # Module dependencies
├── content/                  # Site content
│   ├── _index.md            # Homepage
│   ├── about/
│   ├── life_snippets/
│   └── posts/               # 1000+ blog posts
├── layouts/                 # Custom layouts (if any)
├── static/                  # Static assets
├── assets/img/              # Images and media
├── public/                  # Generated site output
└── resources/               # Hugo resource cache
```

---

## Development Workflow

### Local Development
```bash
# Install dependencies
hugo mod get -u

# Start dev server
hugo server -D  # Include drafts

# Build for production
hugo
```

### Publishing
- Branch-based: Main branch deploys automatically
- Output: `public/` directory
- Hosting: Static site ready for any CDN

---

## Resources & Documentation

- **Hugo**: https://gohugo.io/
- **Blowfish Theme**: https://blowfish.page/
- **Blowfish Docs**: https://blowfish.page/docs/
- **Markdown Syntax**: https://www.markdownguide.org/

---

*Last Updated: May 29, 2026*
