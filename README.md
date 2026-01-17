# Labor with Love - Doula Services Website

A Bridgetown-powered website for **Labor with Love**, Rebecah Hatchel's doula practice in Rochester, New York.

## Important Names

- **Business Name**: Labor with Love (not "Labor of Love")
- **Domain**: laborwithlove.net
- **Email**: hello@laborwithlove.net
- **Instagram**: [@laborwithloveroc](https://www.instagram.com/laborwithloveroc)

## Hosting

- **Host**: GitHub Pages
- **Custom Domain**: laborwithlove.net (DNS via DNSimple)
- **Note**: stephaniewilkinson.github.io is used by the `portfolio` repo (stephaniewilkinson.com)

### Troubleshooting Notes

- **Do NOT remove and re-add the custom domain** - this delays certificate provisioning, not fixes it
- HTTPS certificate provisioning can take time; just wait for GitHub to complete it
- DNS is configured correctly with A records pointing to GitHub's IPs
- **CNAME for www**: Points to `stephaniewilkinson.github.io` (no path needed, even though that's the portfolio site). GitHub routes based on the CNAME file in each repo, not the URL path.
- The main `stephaniewilkinson.github.io` serves the portfolio repo (stephaniewilkinson.com), but custom domains route to the correct repo via CNAME file matching.

## Brand Assets

All brand assets are located in `src/images/`:

| File | Description | Usage |
|------|-------------|-------|
| `heart_icon.svg` | Heart brand icon | Favicon, brand mark |
| `logo-color.svg` | Full color logo (no background) | Header/navbar |
| `logo-white.svg` | White logo (no background) | Footer (dark backgrounds) |
| `logo-black.svg` | Black logo (no background) | Light backgrounds, print |
| `logo-color-bg.svg` | Color logo with background | Featured sections |

### Brand Colors

- **Background**: `#fcf6f7` (soft pink/cream)
- **Primary**: `#6a2b70` (deep purple)
- **Secondary**: `#7d9a78` (sage green) or `#c9a227` (warm gold)
- **Dark text**: Use dark grey/purple, **never pure black**

## Table of Contents

- [Prerequisites](#prerequisites)
- [Install](#install)
- [Development](#development)
- [Deployment](#deployment)

## Prerequisites

- [Ruby](https://www.ruby-lang.org/en/downloads/) `>= 3.2`
- [Node](https://nodejs.org) `>= 20`
- [Bridgetown Gem](https://rubygems.org/gems/bridgetown) - `gem install bridgetown -N`

## Install

```sh
cd laborwithlove
bundle install && npm install
```

## Development

Start the development server:

```sh
bin/bridgetown start
```

Navigate to [localhost:4000](http://localhost:4000/)

### Commands

```sh
# running locally
bin/bridgetown start

# build & deploy to production
bin/bridgetown deploy

# load the site up within a Ruby console (IRB)
bin/bridgetown console
```

## Deployment

Build and copy the `output` folder to your web server, or deploy to hosts like Render, Netlify, or Vercel.

> Read the [Bridgetown Deployment Documentation](https://www.bridgetownrb.com/docs/deployment) for more information.
