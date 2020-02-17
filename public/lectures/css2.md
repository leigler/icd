# CSS Part 2
## Fixed + Sticky Positioning
### Fixed
`position: fixed;` is a commonly used style to &ldquo;fix&rdquo; an element to the page, regardless of scroll position. While recommended to be used as un-nested as possible, you can apply `position: fixed;` to elements whose parents are `position: relative;`. 

- Like `position: absolute;` though, `fixed` will take that element out of the document&rsquo;s flow.
- Any elements inside an element with a `fixed` position will be positioned relative to its parent.

The css for the example in the bottom right corner:

```css

.fixedElement{
	position: fixed;
	right: 1rem;
	bottom: 4rem;
	padding: 1rem;
	background-color: rgba(255,0,0,0.8);
	border: solid 1px black;
	border-radius: 5px;
}

```

<style type="text/css">	
.fixedElement{
	position: fixed;
	right: 1rem;
	bottom: 4rem;
	padding: 1rem;
	background-color: rgba(255,0,0,0.8);
	border: solid 1px black;
	border-radius: 5px;
}
</style>

<div class="fixedElement">This element is fixed!</div>

<br>

### Sticky
`position: sticky;` is a relatively new css style that relies on attributes somewhere between `position: relative;`, `absolute`, and `fixed`:

Position sticky is used to &ldquo;catch&rdquo; elements in relationship to their parents:

<style type="text/css">
		
		.parent{
			width: 60%;
			border-radius: 5px;
			min-height: 30rem;
			padding: 1rem;
			border: 1px solid black;
			font-size: 1rem;
			margin-top: 2rem;
			background-color: rgba(255,255,255,0.8);
			margin-bottom: 2rem;
		}

		.child{
			display: inline-block;
			vertical-align: top;
			width: 50%;
			background-color: red;
			padding: 1rem;
			box-sizing: border-box;
			border: 1px black solid;
		}

		.sticky{
			position: sticky;
			top: 8rem;
		}

		@media(max-width: 768px){
			.parent{
				box-sizing: border-box;
				width: 100%;
			}

			.sticky{
				top: 12rem;
			}
		}


</style>

<div class="parent">
	<div class="child sticky"><p>Some sort of persistent information</p></div
	><div class="child"><p>a larger piece of information Nullam id dolor id nibh ultricies vehicula ut id elit. Cras mattis consectetur purus sit amet fermentum. Vestibulum id ligula porta felis euismod semper. Curabitur blandit tempus porttitor. Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Maecenas sed diam eget risus varius blandit sit amet non magna.</p></div>
</div>


In the css of the *child* element that catches, you will want to define how it catches in relationship to its parent using either the `top` or `bottom` attribute (you can also use the `left` or `right` attributes: especially helpful with horizontal scrolls):

```css

.sticky{
	position: sticky;
	top: 8rem;
}


```


<br><br>\*It&rsquo;s worth noting that `sticky` has some quirks, especially when nested within multiple css `overflow` properties. This medium article is a [good reference](https://uxdesign.cc/position-stuck-96c9f55d9526). 



## Media Queries

CSS allows us to define when specific styles are implemented using `@media` queries. Their general syntax is outlined below:

```css

@media( attribute: value ){
	/* your styles here */

	.myClass{
		background-color: red;
	}

}

```

Media queries are most often used to define desktop and mobile styles via the `min` and `max-width` properties: 

```css

@media( min-width: 768px ){
	/* desktop styles */

	.myClass{
		font-size: 1rem;
	}

}
```

```css
@media( max-width: 768px ){
	/* mobile styles */

	.myClass{
		font-size: 2rem;
	}

}

```

<br><br>**Important:** CSS reads from top to bottom, so where you put your styles matters: you don&rsquo;t want to accidentally override `@media` styles. The example below will always have a `font-size` of 1rem:

```css
@media( max-width: 768px ){
	/* mobile styles */

	.myClass{
		font-size: 2rem;
	}

}

.myClass{
	font-size: 1rem;
}

```

### Breakpoints
As a general rule, you can&rsquo;t account for all devices. I would recommend allowing your designs to rely on fluid units (`vw` or `%`) and respond to design parameters in your control (hover, column width, etc) rather than try and fit your design exclusively for the newest iPhone (... and all other phones previous and yet to come).

That being said, there are some key breakpoints (moments where a `@media` query is applied) to remember: 

#### 768px
The pixel size 768px is used to target mobile devices:
```css

@media(max-width: 768px){

}

```

#### 1024px
The pixel size 1024px is used to target tablet devices:
```css

@media(max-width: 1024px){

}

```

### Logic
You can also employ basic logic (`and` and or (`,`)) with media queries.


#### And
This example would only apply styles to mobile sizes that do not support hover:

```css

@media (any-hover: none) and (max-width: 768px){

}

```

#### Or
While this example would apply styles to any screen size smaller than 700 or greater than 900 pixels:
```css

@media (max-width: 700px), (min-width: 900px){

}

```

### Other Media Queries

A media query that applies styles if the device supports (or doesn&rsquo;t) hovering:
```css

@media(any-hover: none){

}

@media(any-hover: hover){
	
}

```



