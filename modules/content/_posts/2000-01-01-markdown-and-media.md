---
title: Markdown & Media Cheatsheet
---

## Formatting Text with Markdown

If you want to visually format the copywriting in your course, you'll do that using a punctuation-based language called **Markdown**. Markdown also supports HTML which you'll use for [embedding media](../media) or more complicated formatting if needed.

This guide focuses on editing your course directly through GitHub, which offers a Preview tab above the code editor so you can see how your edits look before you commit your changes and wait for them to appear live:

![screenshot of github's Preview Changes function]({{site.baseurl}}/img/preview-changes.png)

If you want to write your text in other software before bringing it into CIAB, here are a few options to convert your formatting into Markdown before bringing it into CIAB:
* Google Docs: [GSuite Tool: Docs to Markdown](https://github.com/evbacher/gd2md-html/wiki#installing-docs-to-markdown)
* Microsoft Word: [Word to Markdown Converter](https://word2md.com/)
* [StackEdit: a visual in-browser Markdown editor](https://stackedit.io/app#)

<br>

## Markdown Cheatsheet
Below are previews of Markdown formatting options and the code needed to make them happen. We've added the most common options here — for more, check out [Mastering Markdown](https://guides.github.com/features/mastering-markdown/).

<br>

----
#### Emphasis 

```
Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with double **asterisks** or __underscores__.

Combined emphasis with **_asterisks and underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~
```

Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with double **asterisks** or __underscores__.

Combined emphasis with **_asterisks and underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~

<br>

----

#### Headings

```
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

<br>

----

#### Bulleted + Numbered Lists

```
* list item
* list item
  * indented list item (two spaces before the *)
    * secondary indented list item (four spaces before the *)
```

* list item
* list item
  * indented list item 
    * secondary indented list item 
    
```
1. numbered list item 1
1. numbered list item 2
1. numbered list item 3
  * mixed list 1 
  * mixed list 2
```

1. numbered list item 1
1. numbered list item 2
1. numbered list item 3
  * mixed list 1 
  * mixed list 2
 
<br>

----

#### Links

Markdown supports a few types of links, but we're just sharing the most common version here. For more details, see [Markdown Links](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#links).

```
[External link](https://p2pu.org)
```

[External link](https://p2pu.org)
 
<br>

----

#### Fancy Buttons
(This is HTML, not Markdown, but just in case you want to get fancy...)

```
<a class="btn btn-primary" href="link address"><i class="fa fa-home"></i> A fancy button</a>
```

<a class="btn btn-primary" href="https://www.p2pu.org/en/"><i class="fa fa-home"></i> A fancy button</a>

<br>

## Adding Media

While Markdown supports adding images, its capacities for media are generally limited. Fortunately, Markdown is designed to support and work alongside HTML which has vast options for customizing your course content with images, videos, and other interactive features.

<br>

#### Media cheatsheet

----
##### Using Existing Images
If you're using an image that is already uploaded somewhere, you can copy the URL and use it like in the example below:

```
![alt](https://www.p2pu.org/assets/images/p2pu-logo.png)
```

![alt text for image](https://www.p2pu.org/assets/images/p2pu-logo.png)

##### Hosting Images on Github

You can also host images for your course for free through GitHub. Head to the `img` folder, click *Add File > Upload Files* (top right above the list of files), and use the upload tool to add your images. When you add an image to your course, you'll link to it with the code below and replace `logo.png` with the name of the image.

```
![alt]({{site.baseurl}}/img/logo.png)
```
![alt]({{site.baseurl}}/img/logo.png)

<br>

----
##### YouTube Videos
If you want to place a video in your course, the easiest way is to upload it to YouTube and grab the automatically-generated embed code from the **Share** button on the video's YouTube page. You can plop this directly into a submodule's `.md` file.

<iframe width="560" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

```
<iframe width="560" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

<br>