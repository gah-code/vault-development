
---

### ✅ `wordpress_frontend_job_vault.sh`

```bash
#!/usr/bin/env bash

VAULT="WordPress_Frontend_Job_Vault"
mkdir -p "$VAULT"
cd "$VAULT" || exit 1

echo "🌐 Setting up WordPress Frontend Job Vault..."

##############################################################################
# 1) Create Main Sections
##############################################################################
mkdir -p "Core_Concepts"
mkdir -p "Theme_Development"
mkdir -p "Gutenberg_Blocks"
mkdir -p "ACF_and_Custom_Fields"
mkdir -p "Plugins"
mkdir -p "Performance"
mkdir -p "SEO"
mkdir -p "Troubleshooting"
mkdir -p "Job_Prep"
mkdir -p "Mock_Projects"

##############################################################################
# 2) Core Concepts
##############################################################################
core_concepts=(
  "WP_Loop"
  "Template_Hierarchy"
  "Hooks_Actions_Filters"
  "WP_Query"
  "REST_API"
)
for topic in "${core_concepts[@]}"; do
  cat <<EOF > "Core_Concepts/$topic.md"
# $topic

## Summary
(TODO: Write a summary)

## Key Concepts
- 🔹 Point 1
- 🔹 Point 2

## Code Example
\`\`\`php
// Example
\`\`\`

## Related Topics
- [[Theme_Development/Custom_Templates]]
EOF
done

##############################################################################
# 3) Theme Development
##############################################################################
mkdir -p "Theme_Development"
cat <<EOF > "Theme_Development/Custom_Templates.md"
# Custom Templates

## Summary
(TODO: Explain custom templates and how to use them)

## Key Topics
- Template hierarchy
- get_template_part
- Conditional template loading
EOF

cat <<EOF > "Theme_Development/Enqueue_Scripts_Styles.md"
# Enqueue Scripts & Styles

## Summary
(TODO: wp_enqueue_style and wp_enqueue_script best practices)

## Example
\`\`\`php
function my_theme_scripts() {
  wp_enqueue_style('main-css', get_stylesheet_uri());
}
add_action('wp_enqueue_scripts', 'my_theme_scripts');
\`\`\`
EOF

##############################################################################
# 4) Gutenberg Blocks & ACF
##############################################################################
cat <<EOF > "Gutenberg_Blocks/Intro_to_Blocks.md"
# Intro to Gutenberg Blocks

## Summary
(TODO: What are Gutenberg blocks and why they matter)

## Tools
- @wordpress/scripts
- Block.json
EOF

cat <<EOF > "ACF_and_Custom_Fields/ACF_Basics.md"
# ACF Basics

## Summary
(TODO: Using ACF to add fields and display them in templates)

## Example
\`\`\`php
the_field('custom_field_name');
\`\`\`
EOF

##############################################################################
# 5) Performance
##############################################################################
cat <<EOF > "Performance/Optimization_Checklist.md"
# Performance Optimization Checklist

## Summary
(TODO: List of performance improvements)

## Items
- ✅ Lazy loading
- ✅ Image optimization
- ✅ CSS/JS minification
- ✅ Caching
EOF

##############################################################################
# 6) Troubleshooting & Debugging
##############################################################################
cat <<EOF > "Troubleshooting/Common_Issues.md"
# Common Issues

## WP Errors
- ❗ White screen of death
- ❗ Plugin conflicts
- ❗ Broken permalinks

## Fixes
(TODO: Add solutions and StackOverflow links)
EOF

##############################################################################
# 7) Job Preparation
##############################################################################
cat <<EOF > "Job_Prep/Interview_Questions.md"
# Interview Questions

## WordPress
- How does the template hierarchy work?
- How do you enqueue scripts/styles properly?

## Frontend
- What’s the difference between relative and absolute units in CSS?
- Explain specificity and the cascade.

## Tools
- Git
- Browser DevTools
EOF

cat <<EOF > "Job_Prep/Portfolio_Checklist.md"
# Portfolio Checklist

- [ ] ✅ Custom WordPress Theme
- [ ] ✅ Gutenberg Block Project
- [ ] ✅ SEO Audit Demo
- [ ] ✅ Performance Lighthouse Report
- [ ] ✅ GitHub + README setup
EOF

##############################################################################
# 8) Mock Projects
##############################################################################
mkdir -p "Mock_Projects/Custom_Theme_01"
cat <<EOF > "Mock_Projects/Custom_Theme_01/README.md"
# Custom Theme 01

## Goal
Build a responsive marketing site using a custom theme.

## Includes
- Custom header/footer
- ACF fields for homepage hero
- Performance and SEO best practices
EOF

mkdir -p "Mock_Projects/ACF_Gutenberg_Blog"
cat <<EOF > "Mock_Projects/ACF_Gutenberg_Blog/README.md"
# ACF Gutenberg Blog

## Goal
Use ACF blocks to build a blog post layout

## Features
- Dynamic fields
- Custom block styling with SCSS
EOF

##############################################################################
# 9) Create an Index File
##############################################################################
cat <<EOF > "📘 WordPress Job Vault Index.md"
# WordPress Frontend Job Vault Index

## Core Concepts
$(for topic in "${core_concepts[@]}"; do echo "- [[Core_Concepts/$topic|$topic]]"; done)

## Theme Development
- [[Theme_Development/Custom_Templates]]
- [[Theme_Development/Enqueue_Scripts_Styles]]

## Gutenberg & ACF
- [[Gutenberg_Blocks/Intro_to_Blocks]]
- [[ACF_and_Custom_Fields/ACF_Basics]]

## Performance
- [[Performance/Optimization_Checklist]]

## Troubleshooting
- [[Troubleshooting/Common_Issues]]

## Job Prep
- [[Job_Prep/Interview_Questions]]
- [[Job_Prep/Portfolio_Checklist]]

## Mock Projects
- [[Mock_Projects/Custom_Theme_01/README]]
- [[Mock_Projects/ACF_Gutenberg_Blog/README]]
EOF

echo "✅ WordPress Frontend Job Vault setup complete!"
```

---

### 🛠 How to Use

1. Save the script above as `wordpress_frontend_job_vault.sh`
2. Make it executable:

   ```bash
   chmod +x wordpress_frontend_job_vault.sh
   ```

3. Run it:

   ```bash
   ./wordpress_frontend_job_vault.sh
   ```

Let me know if you want to add folders for **Git workflows**, **design systems**, **WP CLI**, **accessibility**, or **page builder audits** (like Elementor or Beaver Builder).
