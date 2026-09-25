# Personal Portfolio — Haqiq Azeem Khan

Lab 3 (HTML Advanced - Personal Portfolio II) for CS313 Web Engineering.

The five pages were built in Lab 2. This lab moved all the styling into one
external stylesheet, rebuilt the layouts with `float` and `clear`, organised the
files into folders, and added a responsive breakpoint for small screens.

There is no JavaScript and no CSS framework anywhere in the project.

## Live site

Not published yet. When the repository is pushed and GitHub Pages is switched on,
the site will be at:

    https://haqiqak.github.io/lab3-portfolio-haqiq/

## GitHub

- Username: `haqiqak`
- Repository name: `lab3-portfolio-haqiq`
- Repository URL (after it is created): https://github.com/haqiqak/lab3-portfolio-haqiq

## Pages

| File | What it holds |
|------|---------------|
| `index.html` | About me, a short fact list, and links to the other pages |
| `hobbies.html` | Writing, reading, field hockey and football, game development |
| `skills.html` | Programming and tools, spoken languages, other skills |
| `gallery.html` | Six pictures laid out two per row with float |
| `contact.html` | Contact details in a two column float layout, and a message form |

## Folder structure

```
lab3-portfolio-haqiq/
├── index.html
├── hobbies.html
├── contact.html
├── gallery.html
├── skills.html
├── css/
│   └── style.css
├── images/
│   ├── photo1.jpg
│   ├── photo2.jpg
│   ├── photo3.jpg
│   ├── photo4.jpg
│   ├── photo5.jpg
│   └── photo6.jpg
└── README.md
```

Every page links the stylesheet the same way, with a relative path, so the site
works from a folder, a GitHub Pages URL, or a local file:

```html
<link rel="stylesheet" href="css/style.css">
```

## How float and clear are used

- `.brand` floats left and `.site-nav` floats right, so the name and the menu
  sit on one row. A clearfix on `.bar` keeps them inside the green band.
- `.about-photo` floats right on the home page and left on the reading section of
  the hobbies page, with a `<div class="clear"></div>` after the text so the next
  section starts below it.
- `.gallery figure` floats left at half the width, two per row. The even figures
  lose their right margin so the edge stays flush, and the odd figures use
  `clear: both` to drop below the taller image in the row above.
- `.contact-grid` floats left in the same two column way.
- Below 760px a media query sets every float back to `none` and the widths to
  100%, so the layout stacks into a single column on a phone.

## Images

All six images are stored in `images/` and referenced with relative paths such as
`images/photo1.jpg`, so nothing depends on an outside host staying online.

| File | Shows | Source and licence |
|------|-------|--------------------|
| `photo1.jpg` | NUST campus, Islamabad | NUST Campus Life, `campuslife.nust.edu.pk` |
| `photo2.jpg` | Faisal Mosque, Islamabad | Supplied for this project; a watermark is visible in the bottom right corner |
| `photo3.jpg` | Karachi beach at sunset | Supplied for this project |
| `photo4.jpg` | Jinnah Sports Stadium | Wikimedia Commons, `Jinnah_Sports_Stadium_track_and_field.jpg`, CC BY-SA 4.0 |
| `photo5.jpg` | National Library of Pakistan | Wikimedia Commons, `National_library_of_pakistan.jpg`, CC BY-SA 4.0 |
| `photo6.jpg` | Substack logo mark | Supplied for this project. Shown at its own size because it is a logo, not a photograph |

## Accessibility and small details

- Every image has an `alt` description.
- Form fields have real `<label>` elements tied to their inputs with `for`/`id`.
- A "Skip to content" link is the first thing in the body and only becomes
  visible when it is focused.
- Colour is never the only way information is shown. The active page in the menu
  is marked by position and by an underline as well as by colour.
- The contact form has no JavaScript, so it hands the message to the visitor's
  email client with a `mailto:` action.
