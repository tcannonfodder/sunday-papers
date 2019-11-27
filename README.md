# Sunday Papers: A Nanoc skeleton for Webcomics

Hosting Webcomics should be easy and fast. You shouldn't need Wordpress, another CMS, or a complicated script to publish your comics.

I'm making Sunday Papers in the hopes that it'll help webcomic artists quickly set up their own websites.

_This is a **very** early version. I'm hoping to polish it more in the future. If you have any questions, please feel free to [submit an issue](https://github.com/tcannonfodder/sunday-papers/issues) or reach out some other way, and I'll try to help!_

You see a demo of the skeleton in action here: https://sunday-papers.netlify.com

## How it works

Sunday Papers uses [nanoc](https://nanoc.ws) which is a static site generator that uses the [Ruby programming language](https://www.ruby-lang.org/en/)

The benefits with using a static site generator are:

- There's no need to fiddle with a CMS on a server.
- You can still use templates to quickly update your site.
- The site is built as a series of files on your computer, so it’s easy to test on your own computer & not break your site.
- Changing servers is as easy as uploading files elsewhere

You put all your site's files in the `content/` folder, and then run a special command to build the site. Once the site is built, you can check it on your computer, and then upload it to your server!

## How to use

### Getting your own copy

You can click the "Clone or download" button, then click "Download ZIP" to download the files.

(If you're like me and you use git a lot, you can make a fork of this repository)

### Installation

You'll need to install Ruby and Bundler first:

* [Installing Ruby](https://www.ruby-lang.org/en/documentation/installation/)
* [Installing Bundler](https://bundler.io)

Once they're both installed, you can install Nanoc and a simple webserver by running this command in a terminal:

```sh
bundle install
```

### How the site is structured

These are the main files & folders to worry about when building your site:

* **`content/`**: This is where all the content for your site goes.
* **`content/comic`**: This is where you build the HTML pages for each comic
* **`content/pages`**: This is where I put the image files that make up the comic pages
* **`content/archive.html`**: This is a basic archive page
* **`content/stylesheet.css`**: This is the CSS file you can use to style your site
* **`content/atom.xml`**: This is where you define the [Atom Feed](https://en.wikipedia.org/wiki/Atom_(standard)) for your site
* **`layouts/default.html`**: This is where you define the template used for your site
* **`output/`**: This is where your exported site will be. Once your site is exported, you can copy and paste everything in this folder to your hosting!


### How to build your site

#### Creating a new page

1. Copy one of the example pages that are in `content/comic` (or copy your latest page)
2. Export your pages to the `content/pages/` folder
2. Update the `title` and `created_at` (make sure to keep the `kind: article` line, it's used by Nanoc for some magic ✨)
3. Write the HTML for this page in the `content_for(:comic)` section
4. If you want to write a newspost, write the HTML for it in the `content_for(:newspost)` section


#### Changing the template

The HTML for the template is in: `layouts/default.html`, and the stylesheet is in `content/stylesheet.css`

Don't forget to update the Atom feed for your site at `content/atom.xml`!


#### Compiling and viewing the site

[Nanoc has a good tutorial section that goes over building and viewing your site](https://nanoc.ws/doc/tutorial/#compile-the-site)