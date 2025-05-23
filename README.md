# KV Internal Documentation

This repository contains internal documentation and runbooks for KV systems and processes. The documentation is hosted using GitHub Pages and organized into categories for easy navigation.

## Structure

```
.
├── docs/
│   ├── runbooks/
│   │   ├── incident response/     # Incident response runbooks
│   │   │   ├── index.md          # Category landing page
│   │   │   └── redis-node-down.md
│   │   └── index.md              # Runbooks landing page
│   ├── internal_docs/
│   │   ├── doppler/              # Doppler system documentation
│   │   │   ├── index.md          # System landing page
│   │   │   └── common-kube-operations.md
│   │   └── index.md              # Internal docs landing page
│   └── assets/
│       ├── images/               # Images and diagrams
│       └── css/                  # Custom styling
├── _config.yml                   # Jekyll configuration
├── index.md                      # Main landing page
└── README.md                     # This file
```

## Adding New Documentation

### Creating a New Runbook

1. Identify the appropriate category under `docs/runbooks/`
2. If creating a new category:
   ```
   mkdir docs/runbooks/your-category
   ```
3. Create category index.md (if new):
   ```yaml
   ---
   layout: default
   title: Your Category
   parent: Runbooks
   has_children: true
   nav_order: 1
   ---
   ```
4. Create your runbook markdown file:
   ```yaml
   ---
   layout: default
   title: Your Runbook Title
   parent: Your Category
   grand_parent: Runbooks
   nav_order: 1
   ---
   ```

### Creating New Internal Documentation

1. Identify the appropriate system under `docs/internal_docs/`
2. If documenting a new system:
   ```
   mkdir docs/internal_docs/your-system
   ```
3. Create system index.md (if new):
   ```yaml
   ---
   layout: default
   title: Your System
   parent: Internal Documentation
   has_children: true
   nav_order: 1
   ---
   ```
4. Create your documentation markdown file:
   ```yaml
   ---
   layout: default
   title: Your Doc Title
   parent: Your System
   grand_parent: Internal Documentation
   nav_order: 1
   ---
   ```

### Linking Between Documents

Use Jekyll's link tag to create links between documents:

```markdown
[Link Text]({% link docs/path/to/document.md %})
```

Example:
```markdown
See the [Common Kubernetes Operations]({% link docs/internal_docs/doppler/common-kube-operations.md %}) guide.
```

## Local Development

1. Install Ruby and Bundler
2. Install dependencies:
   ```bash
   bundle install
   ```
3. Run the local server:
   ```bash
   bundle exec jekyll serve
   ```
4. Visit http://localhost:4000

### Troubleshooting Local Development

If you encounter port conflicts:
```bash
bundle exec jekyll serve --port 4001
```

For Ruby 3.4+ users, ensure these gems are in your Gemfile:
```ruby
gem "csv"
gem "base64"
gem "logger"
```

## Contributing Guidelines

### Document Organization

1. Use clear, descriptive titles
2. Place documents in appropriate categories
3. Create new categories when needed
4. Use consistent front matter

### Content Guidelines

1. Write clear, concise instructions
2. Include prerequisites
3. Use code blocks with syntax highlighting
4. Add relevant screenshots or diagrams
5. Link to related documents

### Markdown Best Practices

1. Use headers for organization (##, ###)
2. Use lists for steps and items
3. Use code blocks for commands and examples
4. Use tables for structured data
5. Use callouts for important notes:

```markdown
{: .note }
Important information here.
```

### Front Matter Guidelines

1. Always include required fields:
   - layout
   - title
   - parent
2. Include optional fields as needed:
   - nav_order
   - has_children
   - grand_parent

## Deployment

The documentation is automatically deployed via GitHub Pages when changes are pushed to the main branch.

## Style Guide

### Headers

- Use Title Case for H1 (#)
- Use Sentence case for H2 and below (##, ###)

### Code Blocks

- Include language identifier
- Use inline code for short commands
- Use block code for longer examples

### Links

- Use descriptive link text
- Use Jekyll link tag for internal links
- Include hover text for external links

### Images

1. Store in `assets/images/`
2. Use descriptive file names
3. Include alt text
4. Optimize for web

## Additional Resources

- [Just the Docs Documentation](https://just-the-docs.github.io/just-the-docs/)
- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)