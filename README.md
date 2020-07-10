# plugin-glightbox
A Glightbox plugin for Micro.blog that can be used by other Hugo sites

## Description
[GLightbox](https://biati-digital.github.io/glightbox/) is a great, simple image gallery plugin. It provides an attractive way to show zoomed in versions of your photos when clicking on them, including the ability to have titles, captions, and arrow key/touch navigatable galleries.

This plugin provides a [Hugo shortcode](https://gohugo.io/content-management/shortcodes/) for your Micro.blog (this can be easily used with other Hugo blogs as well) that makes it easy to add these galleries/lightboxes to your site.

## Usage

Using shortcodes are easy. They have a special delimiter, but otherwise, look a lot like HTML. The simplest version of GLightbox works like this:

```html
{{< glightbox src="path-to-image" >}}
```

This will display the image at the URL in `src`. That image will be clickable and will expand in a lightbox.

Adding important accessiblity functions like alt text is as easy as adding an `alt` parameter:

```html
{{< glightbox src="path-to-image" alt="My alt text here" >}}
```

Other optional parameters include:

- `title`, which will show up when you click to expand
- `description`, which will appear below the title (or just below the image if there is no title) upon expansion
- `thumb`, another image URL which will be used as a thumbnail in the non-expanded version on your page. This is especially helpful if your post will have many images.
- `gallery`, which is a name you want to give to an image gallery. To have a navigatable image gallery, you must provide the same text to gallery for all the images that are to be grouped together. It's important this name is somewhat unique, because it's quite possible you'll have multiple galleries on the same page on site indexes or archives, and you'll want to make sure you don't use something like `"gallery1"` in all your posts that puts them all in the same gallery on under these conditions.

## Extras

I have included a small snippet of CSS for anything with the class `img-gallery` that will provide a grid-of-images if you surround your `glightbox` entries with a div of that class.

On my own site, you can see an example on [this blog post.](https://micro.json.blog/2020/01/01/the-first-ten.html)

Here's the code for that first gallery that is in the content of my post:

```html
<div class="img-gallery">
  {{<glightbox src="https://www.json.blog/img/2010-01-30_20-24-32.jpg" thumb="https://www.json.blog/img/2010-01-30_20-24-32_thumb.jpg" gallery="2010" title="Elsa and I Being Playful " description="This is one of the first pictures I have of Elsa and I together. " >}}
  {{<glightbox src="https://www.json.blog/img/2010-04-30_10-37-48.jpg" thumb="https://www.json.blog/img/2010-04-30_10-37-48_thumb.jpg" gallery="2010" title="Elsa, Sinnjinn, and I at Trinity Brewhouse " >}}
  {{<glightbox src="https://www.json.blog/img/2010-06-23_14-06-32.jpg" thumb="https://www.json.blog/img/2010-06-23_14-06-32_thumb.jpg" gallery="2010" title="Signing Ceremony for Rhode Island Funding Formula " description="One of my first professional accomplishments was working on the modeling and language to support new legislation to change how school districts are funded by the state in Rhode Island. This is a picture I grabbed at the signing ceremony." >}}
  {{<glightbox src="https://www.json.blog/img/2010-08-08_13-43-31a.jpg" thumb="https://www.json.blog/img/2010-08-08_13-43-31a_thumb.jpg" gallery="2010" title="Elsa and I Visting Newport, RI " description="From a day trip we took that first summer together down to the mansions in Newport. Note the awesome Glassjaw shirt I've got on." >}}
  {{<glightbox src="https://www.json.blog/img/2012-03-26_21-29-11.jpg" thumb="https://www.json.blog/img/2012-03-26_21-29-11_thumb.jpg" gallery="2010" title="Elsa looking cool " >}}
</div>
```
