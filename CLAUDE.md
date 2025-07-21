# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
This is Ang Hou Fu's personal website (houfu.github.io), a Hugo-based static site focused on legal technology, programming, and personal projects. The site is deployed automatically to GitHub Pages.

## Development Commands

### Local Development
```bash
# Start Hugo development server
hugo server -D --bind 0.0.0.0

# Build for production (same as CI/CD)
hugo --gc --minify --baseURL "https://houfu.github.io/"

# Create new content
hugo new posts/my-new-post.md
hugo new projects/my-project/index.md
```

## Architecture

### Technology Stack
- **Hugo 0.134.0 Extended** (static site generator)
- **hugo-coder theme** with extensive customizations
- **SCSS/CSS** for styling with custom overrides
- **GitHub Actions** for automated deployment

### Directory Structure
- `/content/posts/` - Blog articles (markdown with Hugo front matter)
- `/content/projects/` - Project showcases with detailed descriptions  
- `/content/about/` - Personal/professional information
- `/layouts/shortcodes/` - Custom shortcodes (linkcard, stoot, pdf, video, bluesky)
- `/layouts/_default/` - Custom layout overrides
- `/assets/css/custom.css` - Extensive custom styling
- `/themes/hugo-coder/` - Base theme (do not modify directly)

### Custom Components
The site includes several custom shortcodes for rich content:
- `linkcard` - Preview cards for external links with images
- `stoot` - Mastodon post embedding
- `pdf` - PDF document embedding (used for CV)
- `video` - Video embedding with custom styling
- `bluesky` - Bluesky social media integration
- Mermaid diagram support via custom render hook

### Content Creation
- All content uses Hugo front matter in `+++` format
- Page bundles are supported for content with associated resources
- Categories, series, and tags are configured taxonomies
- Custom CSS classes available for enhanced styling

### Deployment
- Automatic deployment via GitHub Actions on push to master
- Builds with `--gc --minify` flags for optimization
- Timezone set to Asia/Singapore
- Outputs HTML, RSS, and custom SITEXML format

### Theme Customization
- Custom CSS in `/assets/css/custom.css` for UI enhancements
- SCSS variables in `/assets/scss/_variables.scss`
- Dark mode support with automatic color scheme detection
- Responsive design with mobile-first approach

## Configuration Notes
- Main config in `hugo.toml` with social links, navigation, and theme settings
- Gravatar integration for profile images
- Font Awesome icons for social media links
- Twemoji support enabled for emoji rendering