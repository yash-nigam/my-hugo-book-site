# Creating a Hugo Site with Book Theme for Claude Sonnet 3.5

## 1. Initial Setup
```powershell
# Create new site
hugo new site my-hugo-book-site
cd my-hugo-book-site

# Initialize git and create new branch
git init
git checkout -b claudsonnet3.5
```

## 2. Theme Installation
```powershell
# Add Hugo Book theme as submodule
git submodule add -f https://github.com/alex-shpak/hugo-book themes/hugo-book
git submodule init
git submodule update
```

## 3. Configuration Setup
Create `config.toml` with:
```toml
baseURL = "https://yash-nigam.github.io/my-hugo-book-site/"
title = "Claude Sonnet 3.5 Documentation"
theme = "hugo-book"

# Book theme options
[params]
  BookToC = true
  BookRepo = "https://github.com/yash-nigam/my-hugo-book-site"

[menu]
  [[menu.before]]
    name = "Home"
    url = "/"
    weight = 1

  [[menu.before]]
    name = "Docs"
    url = "/docs/"
    weight = 2
```

## 4. Content Creation
```powershell
# Create content directories and files
New-Item -Path "content" -ItemType Directory -Force
New-Item -Path "content\docs" -ItemType Directory -Force
New-Item -Path "content\_index.md" -ItemType File -Force
New-Item -Path "content\docs\_index.md" -ItemType File -Force
```

Create main index file (`content\_index.md`):
```markdown
---
title: Welcome to Claude Sonnet 3.5
type: docs
---

# Claude Sonnet 3.5 Documentation

Welcome to the documentation site for Claude Sonnet 3.5.
```

Create docs index file (`content\docs\_index.md`):
```markdown
---
title: Documentation
weight: 1
---

# Documentation

This section contains detailed documentation for Claude Sonnet 3.5.
```

## 5. Build Site
```powershell
# Generate static files
hugo
```

## 6. GitHub Deployment
```powershell
# Create and switch to public branch
git checkout -b claudsonnet3.5_public

# Save public contents temporarily
New-Item -Path "../temp" -ItemType Directory -Force
Copy-Item -Path "public\*" -Destination "../temp" -Recurse

# Clean branch
Get-ChildItem -Path . -Exclude .git | Remove-Item -Recurse -Force

# Restore public contents
Copy-Item -Path "../temp\*" -Destination "." -Recurse
Remove-Item -Path "../temp" -Recurse -Force

# Push to GitHub
git add .
git commit -m "Deploy Hugo site to GitHub Pages"
git push -u origin claudsonnet3.5_public
```

## 7. GitHub Pages Setup
1. Go to repository Settings
2. Navigate to Pages section
3. Set source branch to `claudsonnet3.5_public`
4. Set folder to `/ (root)`
5. Save changes


Your site will be available at: `https://yash-nigam.github.io/my-hugo-book-site/`
