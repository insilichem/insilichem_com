# InSiliChem.com

InSiliChem website, powered by Hugo and Netlify

# How to add changes

1. Clone the repo.
2. Do NOT modify master at all - create a branch!
3. Work on your changes in the new branch.
4. Test locally with `hugo serve`.
5. If everything looks alright, push and submit a PR to check the temporary website created by netlify.
6. If the preview looks ok, go ahead and merge. Changes will be public after a couple of minutes.
7. If it doesn't, go back to step 3.

# Where to look for changes

## Top bar menu

This is defined in the `config.toml` file:

```
# Navbar Menus
[[menu.nav]]
name    = "About us"
url     = "about"
weight  = 2
[[menu.nav]]
name    = "Blog"
url     = "blog"
weight  = 3
[[menu.nav]]
name    = "Publications"
url     = "publications"
weight  = 4
[[menu.nav]]
name    = "Research"
url     = "research"
weight  = 5
[[menu.nav]]
name    = "Services"
url     = "services"
weight  = 6
[[menu.nav]]
name    = "Software"
url     = "software"
weight  = 7
```

* `name`: Title as displayed in the webpage
* `url`: path within `/content`
* `weight`: position in the menu

## Frontpage sections and text

Hardcoded in `config.toml`, under `[params.banner]`, `[params.about]`, etc.

## Footer and social icons

Footer is hardcoded in `theme/timer-hugo/partials/footer.html`. Other files in directory control how the parameters specified in `config.toml` are rendered (e.g. the banner). If you need more control over that, feel free to edit this file, but careful not to disrupt the HTML code and, specially, its behavior under different display sizes (responsiveness). If you are not sure, better ask first with an issue.

Social icons can be specified in `config.toml`, under `[[params.socialIcon]]`. Create as many entries as needed.

## Content for different sections

Check under `content/<section>`. Each `_index.md` is the main page in that section. Use Markdown for the markup. Depending on the section, they might have an additional template layout specified under `themes/timer-hugo/layouts/<section>/*`. This might or not be useful, so contact for details on how to get rid of this predefined behaviors.

### Research lines
Its information is contained in each respective `data/Research/*.yml` files. The layout is saved in `themes/timer-hugo/layouts/research/list.html`. The option of appearing and disappearing the content of each section is a Jquery, accessible in the js code.

### Publications Section
To include/change papers in the "Our Latest Publications" section, the information is contained in /data/publications.yml directory.
If the "complete list of publications" has to be updated, just add the new papers in /data/allpublications.yml file, generating new items. The layout of this page can be found in `themes/timer-hugo/layouts/allpublications/list.html`.

### Software and services
Under development

### News
This page simply contains a link to twitter. If it has to be modified, its information is contained in `themes/timer-hugo/layouts/news/list.html` directory.

### About Us
To include or change members, `/data/team.yml` and `/data/former_team.yml` are the files that should be modified.

The images of the members have to be scale to 200 x 200 pixels in order to keep the same size in the webpage.


## How to use images

Local images should be copied to `static/images`. You can create as many directories there if you want to categorize by post type, etc. Then, in your content file use standard markdown notation, but removing the `static` part:

Let's say I copied `image.png` into `static/images/example`:

```
![example_image_description](/images/example/image.png)
```

Notice the starting `/` before `images`! Absolute paths are compulsory.

# Questions

Open an issue if there's something not clear and we will try to update this README when necessary.
