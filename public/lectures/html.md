# HTML 
<div class="presentation">
	<h1>HTML</h1>
	<p>(HyperText Markup Language) is the markup language of the web. At its core, HTML is used to create browser-readable documents meant for the distribution of text, images, and other media types.
	</p>
</div>
<div class="presentation">
	<p>As a mental model, I&rsquo;d like to suggest the following quote:</p>
	<blockquote>
		<p>&ldquo;In 2015, Frank Chimero wrote on the <a href="https://frankchimero.com/writing/the-webs-grain/">“Grain” of the Web</a>, focusing on a web-native media that doesn’t try to fight the inherently rectangle-based HTML Document Object Model (DOM) [...] This remains true: any site that does not look rectilinear is usually just fooling you; strip the CSS and it’s just a pile of blocks. Perhaps tilted and stretched, or with the corners shaved off, but just a pile of blocks.&rdquo;
	<br>—from <a target="_blank" href="https://www.are.na/block/736425">Lukas Winkler Prins</a></p>
	</blockquote>
</div>
<div class="presentation">
	<p>And so:</p>
	<ul>
		<li>HTML is a document in which you arrange and re-arrange blocks</li>
		<li>CSS is how we style and shape said blocks</li>
	</ul>
</div>

<div class="presentation">
	<img src="/files/html.jpg">
</div>

<div class="presentation">
	<p>Let&rsquo;s get started:</p>
	<ul>
		<li>If you haven&rsquo;t already, go ahead and download a code editor like <a target="_blank" href="https://www.sublimetext.com/3">Sublime Text 3</a></li>
		<li>Then, go ahead and download the class <a href="/files/boilerplate.zip">Boilerplate</a></li>
		<li>Rename the folder <code>demo-1</code>, and drag the entire folder over the Sublime Text App.</li>
	</ul>
</div>


*** 
# HTML
## Document Set-up
All HTML documents are set-up with three primary actions: 

### A declaration of what the page is: 
```html
<!DOCTYPE html>
<html>

</html>
```

### The creation of a `head` section:
The head section is where we keep information *about* the document, including the site&rsquo;s title, SEO information, and how the document should behave.
```html
<head>
	<title>My First Site</title>
</head>
```

### And finally, the `body` section:
The body section is where we do most of our work: content in this section is read and output by browsers.
```html
<body>
	hello!
</body>
```

### Together, this looks like:
Notice the indentation; organizing your code makes it easy to scan (not to big of a problem with this first page, but as our sites grow to hundreds of lines, indentation will be a live-saver!).
```html
<!DOCTYPE html>
<html>
	<head>
		<title>My First Site</title>
	</head>
	<body>
		hello!
	</body>
</html>
```



## Structure
HTML is built with elements. These elements can be viewed as commands: you are *telling* the browser how it should show content.
Almost all HTML elements (notably excluding the image and horizontal rule tags) follow this structure: 

```html

<element>Element content</element>

```

These elements can be placed inside one another (nested) to make complext organizational groupings: 

```html

<element>
	<element>Element content</element>
</element>

```


## A list of important HTML Elements: 

### Typographic Elements:

- Headers: `h1`, `h2`, `h3`, `h4`, `h5`, `h6` 
- Paragraphs: `p`
- Horizontal rules: `<hr>`
- Unordered lists: `ul`
```html
<ul>
	<li>a list item</li>
	<li>another list item</li>
</ul>
```
- Ordered lists: `ol`

```html
<ol>
	<li>a list item</li>
	<li>another list item</li>
</ol>
```
- code snippets: `<code>some code</code>`
- code blocks: 
```html
<pre>
	<code>some code</code>
</pre>
```

### Organizational Elements + Semantic HTML:
Some HTML elements are used to organize content, often in machine-readable (i.e. accessible) ways:
- Divs (a catch-all wrapper): `div`
- `nav`
- `header`
- `figure`
- `figcaption`
- `main`
- `section`
- `aside`
- `article`
- `footer`


### Media Elements:

- Images: `<img src="path/to/your/file.jpg">`
- Video: 
```html
<video>
	<source src="movie.mp4" type="video/mp4">
</video>
```

*** 

For a complete list: take a look at the [Resources page](/sections/resources)!

