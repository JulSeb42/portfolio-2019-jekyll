# Demo

[Find the demo here](https://www.julien-sebag.fr/templates/portfolio-2019-demo/)

# Documentation for Jekyll

## Install Jekyll

Run in your terminal `gem install jekyll bundler`

## Install Jekyll in your project

Create a new folder. Open it in terminal and run `bundle init`. Then open the Gemfile created and write `gem "jekyll"`. Create your first page. All set!

## Build for production

Open the folder in the terminal and type `bundle exec jekyll build`

## Run website

Open the folder in the terminal and type `bundle exec jekyll serve`. This automatically build the site and creates a host at the address [http://localhost:4000/](http://localhost:4000/)

## Add modifications to content

### Add project

To add a project add a file in `/_projects/` with `name-of-file.md`. In the front matter (between ---) add:
```
---
title: Title of project
order: n (n being the number of the position in the list)
cover: name-of-picture.jpg
company: Name of company
type_company: Type of company
city: City
position: Position
desc: Meta description
next_project: name-of-project
images:
 - path: name-of-picture.jpg
   col: n (n being the number of the position in the list)
   text: Text displayed on the picture
   alt: Alt text for the picture
   link: http://www.link.com (external link, not mandatory)
   video: https://www.youtube.com/embed/-zZbkPnBtS8 (not mandatory, embed YouTube link. To get this link go to the video you want to display, click on Share, then Embed, and just paste here the link in the src)
---
```
For help writing the `.md` file go here: [https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
To add a class to the generated element add `{:.class}` before the line. To add it in a `li` add this at the beginning of the line `* {:.className} `.

Each picture has to come in three different sizes. Append all of them with s, m or l. Ex: `l-cover.jpg`, `m-cover.jpg`, `s-cover.jpg`.

### Add experience

To add an experience open the file `/about.html` and write in the list `experiences`:
```
 - title: Title
   company: Name of company
   city: City
   date: Start Date - End Date
   description: Description
   skills: skills (not mandatory)
```

### Add an education item

To add an experience open the file `/about.md` and write in the list `educations`:
```
 - title: Title
   school: School
   city: City
   date: Start Date - End Date
   description: Description
```

### Add a skill

To add a skill put the logo in SVG or PNG centered in a transparent square (on Illustrator / Sketch / any design software) with dimensions 150x150px and add the file to `assets/images/`. **Use SVG logos when possible**. Then open the file `/about.md` and write in the list `skills`:
```
 - link: https://www.link-to-brand-website.com/
   logo: name-of-logo.svg
```

### Add a language

To add a language open the file `/about.md` and write in the list `languages`:
```
[Language, Language]
```

### Social links and resume

#### In header and footer

Open the file `/_data/social.yml` and write:
```
- name: name-of-social-link
  icon: icon_name-weight
  link: https://www.link-to-website.com/
```

### Add navigation item

Open `/_data/nav.yml` and write:
```
- title: Title displaying in the menu
  link: /path/to/page/
```

## Edit layout

### General

Open the page `/_layouts/default.html` and edit this page. You can add other CSS or JS inside this one.

### Homepage

Edit the page `/index.html`

### Project page

Edit the page `/_layouts/projects.html`

### Header

Edit the page `/_includes/header.html`

### Footer

Edit the page `/_includes/footer.html`

### Social icons list

Edit the page `/_includes/social.html`

## Edit design

### SCSS files

SCSS files are located in the folder `/_sass/`, and are automatically compiled to a minified CSS. To add a new SCSS file to the website add this in the `head` of your HTML in `/_layouts/default.html`:
```
<link rel="stylesheet" href="assets/css/name_of_file.css" />
```

### CSS files

CSS files are located in the folder `assets/css/`. To add it to your website add this in the `head` of your HTML in `/_layouts/default.html`:
```
<link rel="stylesheet" href="assets/css/name_of_file.css" />
```

### CDN CSS files

To add it to your website add this in the `head` of your HTML in `/_layouts/default.html`:
```
<link rel="stylesheet" href="https://www.link-to-cdn.com/name_of_file.css" />
```