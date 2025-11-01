# Minimalist Personal Blog

A simple, minimalist static blog designed to be hosted on Cloudflare Pages.

## Features

- Clean, minimalist design
- Dark mode support (automatic based on system preferences)
- Responsive layout
- Fast loading (no frameworks or dependencies)
- Easy to customize

## Structure

```
.
├── index.html          # Main blog listing page
├── posts/              # Blog post HTML files
│   ├── hello-world.html
│   └── minimalism-in-design.html
├── styles.css          # Main stylesheet
└── README.md           # This file
```

## Adding New Posts

1. Create a new HTML file in the `posts/` directory
2. Use the existing post files as templates
3. Add a link to the new post in `index.html`

Example post structure:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Post Title - Blog</title>
    <link rel="stylesheet" href="../styles.css">
</head>
<body>
    <header>
        <nav>
            <a href="/" class="logo">Blog</a>
        </nav>
    </header>
    
    <main>
        <div class="container">
            <a href="/" class="back-link">← Back to posts</a>
            
            <article>
                <header class="post-header">
                    <h1>Your Post Title</h1>
                    <time datetime="YYYY-MM-DD">Date</time>
                </header>
                
                <div class="post-content">
                    <!-- Your content here -->
                </div>
            </article>
        </div>
    </main>
    
    <footer>
        <p>&copy; 2024</p>
    </footer>
</body>
</html>
```

## Deployment to Cloudflare Pages

### Option 1: GitHub Integration (Recommended)

1. Push this repository to GitHub
2. Go to [Cloudflare Dashboard](https://dash.cloudflare.com/)
3. Navigate to **Pages** → **Create a project**
4. Connect your GitHub account and select this repository
5. Configure build settings:
   - **Framework preset**: None
   - **Build command**: (leave empty)
   - **Build output directory**: `/`
6. Click **Save and Deploy**

### Option 2: Direct Upload via Wrangler CLI

1. Install Wrangler CLI:
   ```bash
   npm install -g wrangler
   ```

2. Login to Cloudflare:
   ```bash
   wrangler login
   ```

3. Deploy:
   ```bash
   wrangler pages deploy .
   ```

### Option 3: Drag and Drop

1. Go to [Cloudflare Pages](https://dash.cloudflare.com/)
2. Create a new project
3. Choose "Upload assets"
4. Zip the project files and upload

## Customization

- **Colors**: Edit CSS variables in `styles.css` (`:root` section)
- **Font**: Change the `font-family` in `styles.css`
- **Logo/Brand**: Update the logo text in the `<nav>` section
- **Footer**: Modify the copyright text in the footer

## Local Development

Simply open `index.html` in a web browser, or use a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js (if you have http-server installed)
npx http-server
```

Then visit `http://localhost:8000`

