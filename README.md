# ARDCO Theme for Alliance Auth (Bootstrap 5)

Complete ARDCO Fuel Company design system for Alliance Auth with Bootstrap 5.

## Features

✨ **Authentic ARDCO Design**
- Exact color palette from [ARDCO SPA](https://responsilicious.github.io/ardco-spa/)
- Orbitron font for headings, Rajdhani for body text
- Signature clipped hexagonal corners on all components
- Radial gradient overlays with scanline effects
- Corner accent decorations on cards
- Custom scrollbars with gradient effects

🎨 **Comprehensive Coverage**
- ✅ Navbar (top bar) - fully styled with backdrop blur
- ✅ Sidebar - gradient overlays, scanline effects, clipped menu items
- ✅ Cards - corner accents, gradients
- ✅ Tables - hover effects, accent colors
- ✅ Tabs - multi-level tab support
- ✅ Buttons - all variants with gradients
- ✅ Forms - inputs, selects, checkboxes
- ✅ Badges - clipped corners, status colors
- ✅ Dropdowns - gradient menus
- ✅ Alerts - corner decorations
- ✅ User info section
- ✅ All Bootstrap 5 utilities

## Installation

### Quick Start

Add this CSS file **AFTER** your Bootstrap CSS in your HTML `<head>`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Bootstrap 5 -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
    
    <!-- ARDCO Theme - Add AFTER Bootstrap -->
    <link rel="stylesheet" href="ardco-alliance-auth-theme-bs5.css">
    
    <!-- FontAwesome (if using icons) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
    
    <!-- Bootstrap Icons (if using icons) -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.0/font/bootstrap-icons.css">
</head>
<body>
    <!-- Your content here -->
</body>
</html>
```

### For Alliance Auth

1. **Place the CSS file** in your Alliance Auth static directory:
   ```
   /path/to/allianceauth/myauth/static/css/ardco-theme.css
   ```

2. **Update your base template** (usually `base.html` or similar):
   ```django
   {% load static %}
   <!DOCTYPE html>
   <html>
   <head>
       <!-- Existing Bootstrap CSS -->
       <link href="{% static 'bootstrap/css/bootstrap.min.css' %}" rel="stylesheet">
       
       <!-- Add ARDCO Theme AFTER Bootstrap -->
       <link rel="stylesheet" href="{% static 'css/ardco-theme.css' %}">
   </head>
   ```

3. **Collect static files**:
   ```bash
   python manage.py collectstatic --noinput
   ```

4. **Restart your server**:
   ```bash
   supervisorctl restart myauth:
   # or
   systemctl restart gunicorn
   ```

5. **Clear browser cache** (Ctrl+Shift+R / Cmd+Shift+R)

## Color Palette

The theme uses the official ARDCO colors:

```css
/* Backgrounds */
--ardco-bg: #0b0f17;       /* Main background */
--ardco-panel: #0f1626;     /* Panel background */
--ardco-panel2: #0c1322;    /* Alternate panel */

/* Text */
--ardco-text: #e9eefc;      /* Primary text */
--ardco-muted: #a9b5d1;     /* Secondary text */

/* Accents */
--ardco-accent: #7aa7ff;    /* Primary blue */
--ardco-accent2: #6ee7ff;   /* Cyan */
--ardco-success: #7CFFB2;   /* Green */
```

## Customization

### Override Colors

Create a custom CSS file that loads after the ARDCO theme:

```css
/* custom-colors.css */
:root {
  /* Override ARDCO colors */
  --ardco-accent: #ff6b00;      /* Orange instead of blue */
  --ardco-accent2: #ffd700;     /* Gold instead of cyan */
  --ardco-success: #00ff9d;     /* Bright green */
}
```

Load it after the ARDCO theme:

```html
<link rel="stylesheet" href="ardco-alliance-auth-theme-bs5.css">
<link rel="stylesheet" href="custom-colors.css">
```

### Disable Effects

To disable specific visual effects:

```css
/* Disable gradient overlays */
body::before {
  display: none !important;
}

/* Disable scanline effect */
body::after {
  display: none !important;
}

/* Disable clipped corners */
.card,
.btn,
.badge {
  clip-path: none !important;
  border-radius: 0.5rem !important;
}
```

### Font Changes

To use different fonts:

```css
:root {
  --ardco-font-heading: 'Your Heading Font', sans-serif;
  --ardco-font-body: 'Your Body Font', sans-serif;
}

h1, h2, h3, h4, h5, h6 {
  font-family: var(--ardco-font-heading) !important;
}

body {
  font-family: var(--ardco-font-body) !important;
}
```

## Component Examples

### Clipped Corner Button
```html
<button class="btn btn-primary">
  <i class="bi bi-plus-lg"></i> Add Character
</button>
```

### Card with Corner Accents
```html
<div class="card">
  <div class="card-header">
    <h5 class="mb-0">Corporation ESI</h5>
  </div>
  <div class="card-body">
    <!-- Content -->
  </div>
</div>
```

### Styled Table
```html
<table class="table table-hover">
  <thead>
    <tr>
      <th>Character</th>
      <th>Corporation</th>
      <th>Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>CaptainThorVonAwesome</td>
      <td>ARDCO</td>
      <td><span class="badge bg-success">Valid</span></td>
    </tr>
  </tbody>
</table>
```

### Tabs
```html
<ul class="nav nav-tabs" role="tablist">
  <li class="nav-item">
    <button class="nav-link active" data-bs-toggle="tab" data-bs-target="#orders">
      <i class="bi bi-list-ul"></i> Orders
    </button>
  </li>
  <li class="nav-item">
    <button class="nav-link" data-bs-toggle="tab" data-bs-target="#contracts">
      <i class="bi bi-file-earmark-text"></i> Contracts
    </button>
  </li>
</ul>
```

## Browser Support

- ✅ Chrome/Edge (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)
- ⚠️ IE11 (degraded experience - no clip-path, CSS variables)

## Troubleshooting

### Styles Not Applying

1. **Check load order**: ARDCO theme must load AFTER Bootstrap
2. **Clear cache**: Hard refresh with Ctrl+Shift+R (Windows/Linux) or Cmd+Shift+R (Mac)
3. **Check file path**: Verify the CSS file is in the correct location
4. **Run collectstatic**: For Django/Alliance Auth installations
5. **Check browser console**: Look for 404 errors on the CSS file

### Colors Look Wrong

- Make sure you're not loading a different theme after the ARDCO theme
- Check if there's a `data-theme` attribute on `<html>` overriding colors
- Use browser dev tools to inspect which CSS is actually applied

### Fonts Not Loading

- Check your internet connection (Google Fonts CDN)
- Add fallback fonts in custom CSS if needed
- Consider self-hosting the fonts for offline environments

### Clipped Corners Not Working

- Older browsers don't support `clip-path`
- The theme will gracefully degrade to standard corners
- This is expected behavior and doesn't break functionality

## Performance Tips

1. **Combine CSS files** in production for faster loading
2. **Enable gzip compression** on your web server
3. **Use CDN** for Bootstrap and icon libraries
4. **Minify CSS** for production deployments

## Credits

- **Original Design**: ARDCO Fuel Company ([responsilicious.github.io/ardco-spa](https://responsilicious.github.io/ardco-spa/))
- **Fonts**: Orbitron and Rajdhani from Google Fonts
- **Framework**: Bootstrap 5.3.3
- **Alliance Auth**: [gitlab.com/allianceauth/allianceauth](https://gitlab.com/allianceauth/allianceauth)

## License

This theme is provided as-is for use with Alliance Auth and Bootstrap 5 projects.

---

**Not affiliated with CCP Games. EVE Online is a trademark of CCP Games.**
