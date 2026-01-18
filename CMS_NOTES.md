# CMS Architecture Notes

## Sveltia CMS Local Development

Sveltia CMS works differently from Netlify/Decap CMS:

- **No proxy server needed** - Unlike Netlify CMS, Sveltia uses the browser's File System Access API
- **No `local_backend: true` option** - This option is ignored; remove it from config
- **Browser requirement** - Must use Chrome, Edge, or Brave (not Firefox/Safari)

### Local Workflow Steps

1. Run `bin/bridgetown start`
2. Open `http://localhost:4000/admin/index.html` in Chrome/Edge
3. Click **"Work with Local Repository"** button
4. Select the project root folder (`/Users/steph/repos/laborwithlove`)
5. The CMS now has access to read/write local files

### Important

- Changes made in the CMS are written directly to local files
- You must manually commit and push changes with git
- Reload the CMS after modifying `config.yml`

## File Structure

### Homepage

The homepage uses a **data file** for CMS-editable content (not frontmatter):

- **Content**: `src/_data/homepage.yml` - All editable text fields
- **Template**: `src/index.erb` - Reads from `site.data.homepage`
- **Layout**: `src/_layouts/home.erb` - Adds blog posts section automatically
- **Partial**: `src/_partials/_recent_blog_posts.erb` - Shows 3 latest posts

Why this structure:
- Sveltia CMS can read/write YAML data files easily
- ERB templates can't have their frontmatter edited by the CMS (it doesn't parse .erb)
- Separating data from template keeps things clean

### Other Pages

| Page | File | CMS Editable |
|------|------|--------------|
| About | `src/about.md` | Yes - markdown body |
| Contact | `src/contact.erb` | Limited - only frontmatter fields |
| Blog Posts | `src/_posts/*.md` | Yes - full markdown |

### Partials

| Partial | Used By | Purpose |
|---------|---------|---------|
| `_recent_blog_posts.erb` | Homepage (via layout) | Shows 3 latest posts |
| `_contact_form.erb` | Contact page | Netlify form |

## CMS Config Structure

```
collections:
  - posts          # Blog posts (folder collection)
  - homepage       # Homepage content (file: src/_data/homepage.yml)
  - pages          # About, Contact (file collection)
  - settings       # Site metadata (file: src/_data/site_metadata.yml)
```

## Troubleshooting

**CMS shows empty fields:**
- Did you click "Work with Local Repository" and select the folder?
- Are you using Chrome/Edge/Brave?
- Try reloading the admin page

**Changes not appearing on site:**
- Bridgetown may need to rebuild - check if dev server is running
- Some changes require a full page refresh

## References

- [Sveltia CMS Docs](https://sveltiacms.app/en/docs/start)
- [Local Workflow](https://sveltiacms.app/en/docs/workflows/local)
