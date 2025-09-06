# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
This is Ang Hou Fu's personal website (houfu.github.io), a Hugo-based static site focused on legal technology, programming, and personal projects. The site is deployed automatically to GitHub Pages.

## Development Commands

### Local Development
```bash
# Start Hugo development server (includes drafts, binds to all interfaces)
hugo server -D --bind 0.0.0.0

# Stop development server (if running in background)
# Use KillBash tool with the appropriate shell_id

# Build for production (same as CI/CD)
hugo --gc --minify --baseURL "https://houfu.github.io/"
```

### Content Creation Commands
```bash
# Create new post as page bundle (PREFERRED METHOD)
# 1. Create folder: content/posts/my-post-name/
# 2. Create index.md inside the folder
# 3. Add images directly to the same folder

# Legacy single file method (avoid unless necessary)
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
  - Most posts are page bundles: `content/posts/post-name/index.md` with images in same folder
  - Example: `content/posts/japan-trip-copilot-studio-no-code/index.md` + images
  - Legacy single files: `content/posts/post-name.md` (older posts)
- `/content/projects/` - Project showcases with detailed descriptions  
- `/content/about/` - Personal/professional information
- `/layouts/shortcodes/` - Custom shortcodes (linkcard, stoot, pdf, video, bluesky)
- `/layouts/_default/` - Custom layout overrides
- `/assets/css/custom.css` - Extensive custom styling
- `/themes/hugo-coder/` - Base theme (do not modify directly)

### Content Categories and Topics
The blog focuses on legal technology and programming with these main categories:
- **Legal Tech**: AI tools, automation, no-code solutions for legal work
- **Programming**: Coding tutorials, technical implementations, developer experiences  
- **Work**: Professional experiences, business travel insights, career development
- **Projects**: Personal coding projects, experiments, and technical showcases

Common topics include: Microsoft Copilot Studio, DocAssemble, prompt engineering, legal automation, AI agents, no-code tools, Python programming, legal document processing

### Finding Previous Posts for Reference

To quickly understand existing content and find related posts:

```bash
# List all posts
Glob "content/posts/**/*.md"

# Search by topic/keyword
Grep "copilot" --glob "content/posts/**/*.md"
Grep "legal" --glob "content/posts/**/*.md" 

# Read post summaries (front matter + opening paragraphs)
Read file_path limit=30
```

**Front matter includes**: title, description, tags, categories, date, series
**Opening paragraphs** provide context and main themes

**Workflow for referencing existing content**:
1. Search by relevant keywords to find related posts
2. Read first 30 lines of relevant posts to understand scope and approach
3. Reference similar posts when writing new content or providing context
4. Check tags and categories to understand content classification patterns

### Custom Components
The site includes several custom shortcodes for rich content:
- `linkcard` - Preview cards for external links with images
- `stoot` - Mastodon post embedding
- `pdf` - PDF document embedding (used for CV)
- `video` - Video embedding with custom styling
- `bluesky` - Bluesky social media integration
- Mermaid diagram support via custom render hook

### Content Creation
- **ALWAYS prefer page bundles for new posts** - create folder with index.md + images
- All content uses Hugo front matter in `+++` format
- Page bundles are supported for content with associated resources
- Categories, series, and tags are configured taxonomies
- Custom CSS classes available for enhanced styling
- Images should be placed in the same folder as index.md for page bundles

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

## Available Specialized Agents

When working on this project, the following Claude Code agents are available and recommended:

- **legal-tech-blog-reviewer**: Use for feedback on blog posts from the perspective of lawyers who code and legal technologists
- **inhouse-lawyer-reviewer**: Use for feedback from the perspective of corporate lawyers with limited resources  
- **content-quality-auditor**: Use for comprehensive quality control on blog posts and articles
- **blog-skeleton-generator**: Use to create new Hugo blog post structures with appropriate front matter and content outline

## Configuration Notes
- Main config in `hugo.toml` with social links, navigation, and theme settings
- Gravatar integration for profile images
- Font Awesome icons for social media links
- Twemoji support enabled for emoji rendering