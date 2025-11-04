# Path Reference Guide

This document provides the correct paths for different file types in the website structure.

## Current Directory Structure

```
html/
├── articles/
│   ├── en/
│   │   ├── infrastructure/
│   │   ├── automation_ai/
│   │   ├── docker_services/
│   │   ├── network_security/
│   │   ├── reference/
│   │   └── remote_access/
│   └── fr/
│       ├── infrastructure/
│       ├── automation_ai/
│       ├── network_security/
│       └── remote_access/
├── css/
│   ├── styles.css
│   ├── responsive.css
│   └── animations.css
├── js/
│   ├── main.js
│   └── animations.js
├── blog/
│   ├── blog.css
│   ├── blog.js
│   └── *.html
└── *.html (main pages)
```

## Correct Paths by File Type

### Articles in /en/ and /fr/ Subdirectories

From: `articles/en/category/article.html` or `articles/fr/category/article.html`

```html
<!-- CSS Files -->
<link rel="stylesheet" href="../../../css/styles.css">
<link rel="stylesheet" href="../../../css/responsive.css">
<link rel="stylesheet" href="../../../css/animations.css">
<link rel="stylesheet" href="../../../blog/blog.css">

<!-- JavaScript Files -->
<script src="../../../js/main.js"></script>
<script src="../../../js/animations.js"></script>
<script src="../../../blog/blog.js"></script>

<!-- Navigation Links -->
<a href="../../../index.html">Home</a>
<a href="../../../blog/index.html">Blog</a>
<a href="../../../blog/category.html">Category</a>
```

### Blog Pages

From: `blog/category.html` or `blog/index.html`

```html
<!-- CSS Files -->
<link rel="stylesheet" href="../css/styles.css">
<link rel="stylesheet" href="../css/responsive.css">
<link rel="stylesheet" href="../css/animations.css">
<link rel="stylesheet" href="blog.css">

<!-- JavaScript Files -->
<script src="../js/main.js"></script>
<script src="../js/animations.js"></script>
<script src="blog.js"></script>

<!-- Navigation Links -->
<a href="../index.html">Home</a>
<a href="index.html">Blog Index</a>
```

### Main Pages

From: `index.html` or other root-level pages

```html
<!-- CSS Files -->
<link rel="stylesheet" href="css/styles.css">
<link rel="stylesheet" href="css/responsive.css">
<link rel="stylesheet" href="css/animations.css">
<link rel="stylesheet" href="blog/blog.css">

<!-- JavaScript Files -->
<script src="js/main.js"></script>
<script src="js/animations.js"></script>
<script src="blog/blog.js"></script>
```

## Path Calculation Rules

1. **Count the levels up** from the current file to the html/ root directory
2. **Use that many "../"** in the path
3. **Add the target directory** (css/, js/, blog/)

### Examples:

- From `articles/en/infrastructure/article.html` → `../../../css/` (3 levels up)
- From `blog/infrastructure.html` → `../css/` (1 level up)
- From `index.html` → `css/` (0 levels up)

## Common Mistakes to Avoid

1. **Using old paths**: `../../css/` instead of `../../../css/` in articles
2. **Inconsistent paths**: Mixing relative and absolute paths
3. **Wrong blog CSS path**: `../blog/blog.css` instead of `../../blog/blog.css` in articles
4. **Missing navigation fixes**: Forgetting to update index.html and blog links

## Testing

After making path changes, test:

1. **CSS Loading**: Check if dark theme and styling apply correctly
2. **JavaScript Functionality**: Verify navigation, interactions, and animations work
3. **All Links**: Test navigation, breadcrumbs, and footer links
4. **Responsive Design**: Test on different screen sizes
5. **Both Languages**: Test both English and French articles

## Automation

Use the provided scripts for automated fixes:

- `fix-article-paths.sh`: Comprehensive fix script with backup and logging
- `fix-all-article-paths.sh`: Quick fix script for immediate repairs
- `rollback-article-paths.sh`: Restore from backup if needed

## Recent Fix Summary

**Date**: 2025-11-04  
**Problem**: CSS and JS paths broken after language reorganization  
**Root Cause**: Articles moved to deeper directory structure (added /en/ and /fr/)  
**Solution**: Updated all relative paths from `../../` to `../../../` in article files  

**Files Fixed**:
- All HTML files in `articles/en/*/` directories
- All HTML files in `articles/fr/*/` directories
- CSS, JS, and navigation links updated

**Commands Used**:
```bash
# Fix CSS paths
find articles/ -name "*.html" -type f -exec sed -i 's|href="../../css/|href="../../../css/|g' {} \;

# Fix JS paths  
find articles/ -name "*.html" -type f -exec sed -i 's|src="../../js/|src="../../../js/|g' {} \;

# Fix blog paths
find articles/ -name "*.html" -type f -exec sed -i 's|href="../../blog/|href="../../../blog/|g' {} \;

# Fix navigation links
find articles/ -name "*.html" -type f -exec sed -i 's|href="../../index.html|href="../../../index.html|g' {} \;
```

## Verification

After fixes, verify:
- ✅ CSS loads correctly (dark theme visible)
- ✅ JavaScript works (navigation, interactions)
- ✅ All links navigate properly
- ✅ Both English and French articles functional
- ✅ Blog pages remain unaffected