---
title: Getting Started with Astro
description: A beginner-friendly guide to building your first website with Astro framework.
category: tutorial
pubDatetime: 2024-03-15T16:00:00Z
tags: ["astro", "web-development", "tutorial", "beginners"]
---

# Getting Started with Astro

This tutorial will guide you through creating your first website using Astro, a modern static site generator that delivers lightning-fast performance.

## Prerequisites

Before we begin, make sure you have:
- Node.js (version 18 or later)
- A code editor (VS Code recommended)
- Basic knowledge of HTML, CSS, and JavaScript

## Creating Your First Astro Project

1. Open your terminal and run:
```bash
# Create a new project with npm
npm create astro@latest

# Or with pnpm
pnpm create astro@latest
```

2. Follow the CLI prompts:
   - Enter your project name
   - Choose a template (start with "Basic" for this tutorial)
   - Initialize a git repository if desired

## Project Structure

After creation, your project will have this structure:
```
your-project/
├── public/
├── src/
│   ├── components/
│   ├── layouts/
│   └── pages/
├── astro.config.mjs
└── package.json
```

## Creating Your First Page

1. Create a new file `src/pages/about.astro`:
```astro
---
// Component Script (optional)
const pageTitle = "About Me";
---

<html lang="en">
  <head>
    <title>{pageTitle}</title>
  </head>
  <body>
    <h1>{pageTitle}</h1>
    <p>Welcome to my Astro site!</p>
  </body>
</html>
```

2. Start the development server:
```bash
npm run dev
```

3. Visit `http://localhost:4321/about` to see your page

## Adding Components

Create a reusable header in `src/components/Header.astro`:
```astro
---
const navItems = ["Home", "About", "Blog"];
---

<header>
  <nav>
    <ul>
      {navItems.map(item => (
        <li>
          <a href={`/${item.toLowerCase()}`}>{item}</a>
        </li>
      ))}
    </ul>
  </nav>
</header>
```

## Using Layouts

1. Create a layout in `src/layouts/BaseLayout.astro`:
```astro
---
const { title } = Astro.props;
import Header from '../components/Header.astro';
---

<html lang="en">
  <head>
    <title>{title}</title>
  </head>
  <body>
    <Header />
    <main>
      <slot />
    </main>
  </body>
</html>
```

2. Use the layout in your pages:
```astro
---
import BaseLayout from '../layouts/BaseLayout.astro';
---

<BaseLayout title="Home">
  <h1>Welcome to my site!</h1>
</BaseLayout>
```

## Next Steps

Now that you have the basics, you can:
1. Add more pages to your site
2. Style your components with CSS
3. Integrate with your favorite frameworks (React, Vue, Svelte)
4. Deploy your site to your preferred hosting platform

Remember to check the [official Astro documentation](https://docs.astro.build) for more advanced features and best practices!
