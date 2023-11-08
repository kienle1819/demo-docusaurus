# 🎉 DEMO Docusaurus Netlify

Netlify: A modern web development platform that streamlines the process from code to deployment. With built-in CI/CD, automated hosting, and serverless functionalities, it empowers developers to focus on building great websites and applications.

![version](https://img.shields.io/badge/version-1.0-blue)
![rating](https://img.shields.io/badge/rating-★★★★★-yellow)
![uptime](https://img.shields.io/badge/uptime-100%25-brightgreen)

### 🚀 Setup

- Create Start Project

```
npx create-docusaurus@latest my-website classic
```

- Make Directory `admin`

```
cd static
mkdir admin
```

- Create File in `admin`

```
cd admin
touch config.yml
touch index.html
```

- Edit `index.html`

```
<!doctype html>
<html>
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Content Manager</title>
</head>
<body>
  <!-- Include the script that builds the page and powers Decap CMS -->
  <script src="https://unpkg.com/decap-cms@^3.0.0/dist/decap-cms.js"></script>
</body>
</html>
```

- Edit `config.yml`

```
backend:
  name: github
  branch: main 
  repo: <your-github>/my-website

# These lines should *not* be indented
media_folder: "static/img" # Media files will be stored in the repo under static/images/uploads
public_folder: "/img/" # The src attribute for uploaded media will begin with /images/uploads

collections:
- name: blog
  label: "blog"
  folder: blog
  identifier_field: title
  extension: md
  widget: "list"
  create: true
  slug: "{{year}}-{{month}}-{{day}}-{{slug}}" # Filename template, e.g., YYYY-MM-DD-title.md
  fields:
    - { name: title, label: Title, widget: string }
    - { name: body, label: Body, widget: markdown }
    - { name: slug, label: Slug, widget: string }
    - label: "Tags"
      name: "tags"
      widget: "list"
    - label: "Authors"
      name: "authors" 
      widget: "list"
      fields:
        - { name: name, label: Name, widget: string }
        - { name: title, label: Title, widget: string } 
        - { name: url, label: URL, widget: string } 
        - { name: imageUrl, label: ImageURL, widget: string } 
```

### 🔑 Configuration

- [New OAuth App in Github](https://github.com/settings/developers)
- [Install OAuth Provider in Netlify](https://app.netlify.com/)

### 🏆 Run

- [https://dainty-flan-38b69b.netlify.app/](https://dainty-flan-38b69b.netlify.app/)
- [https://dainty-flan-38b69b.netlify.app/admin](https://dainty-flan-38b69b.netlify.app/admin)