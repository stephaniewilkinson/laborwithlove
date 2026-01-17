# Labor with Love - Doula Services Website

A Bridgetown-powered website for **Labor with Love**, Rebecah Hatchel's doula practice in Rochester, New York.

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
