# CSS Part 2

## CSS Pseudo Classes

A complete list of Pseudo-classes can be found [here](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes). The general syntax for css pseudo-classes includes the original selector and the defined pseudo-class: 


```css

selector:pseudo-class {
	property: value;
}

```

<br><br>Loosely, we can divide css pseudo classes into two categories: Interactive and Logic-based.

## Interactive

## Brief Interlude

To smoothly transition between states, you may want to explore the CSS attribute, `transition` which accepts a property, duration, and easing:

```css

.myClass{
	background-color: red;
	transition: background-color 0.2s ease-in;
}

```

To list multiple transitions, separate them by comma:

```css

.myClass{
	background-color: red;
	transition: background-color 0.2s ease-in, width 0.5s ease-out;
}

```


#### Hover

```css

.myClass:hover {
	background-color: red;
}

```


#### Focus
Focus states are most often used for forms.
```css

.myClass:focus {
	background-color: green;
}

```


#### Active
Active states are most often used for links and buttons.
```css

.myClass:active {
	background-color: blue;
}

```

#### Visited

```css

.myClass:visited {
	color: yellow;
}

```


<style>
	.exampleSection{
		border: dotted #8A2BE2 1px;
		border-radius: 0.25rem;
		padding: 1rem;
		margin-top: 1rem;
		margin-bottom: 1rem;
		max-width: 60rem;
		box-sizing: border-box;
	}

	.exampleLink{
		display: inline-block;
		background-color: black;
		color: white;
		border-color: black;
		margin-top: 1rem;
		margin-bottom: 1rem;
		padding: 1rem;
	}

	.exampleLink:hover{
		background-color: red;
	}

	.exampleLink:focus{
		background-color: green;
	}

	.exampleLink:active{
		background-color: blue;
	}

	.exampleLink:visited{
		color: yellow;
	}

</style>

<a class="exampleLink" target="_blank" href="/lectures">Example Link</a>	


## Logic

#### First-of-type

```css

.myParagraphs:first-of-type {
	background-color: #8A2BE2;
}

```

#### nth-of-type()
selects a specific or repeating element:

```css

.myParagraphs:nth-of-type(even) {
	border: solid 2px black;
}

.myParagraphs:nth-of-type(5n) {
	border: dotted 4px red;
}

.myParagraphs:nth-of-type(2) {
	border: dashed 2px blue;
}

```

#### :not()

```css

.myParagraphs:not(#special){
	font-style: italic;
	font-family: Helvetica, Arial;
}

```

<style type="text/css">

.myParagraphs{
	width: 50%;
	margin-top: 1rem;
	text-indent: 0;
	padding: 0.25rem;
}

.myParagraphs:not(#special){
	font-style: italic;
	font-family: Helvetica, Arial;
}

.myParagraphs:first-of-type {
	background-color: #8A2BE2;
}
.myParagraphs:nth-of-type(even) {
	border: solid 2px black;
}

.myParagraphs:nth-of-type(5n) {
	border: dotted 4px red;
}

.myParagraphs:nth-of-type(2) {
	border: dashed 2px blue;
}
</style>

<div class="exampleSection">
	<p class="myParagraphs" >First paragraph</p>
	<p class="myParagraphs" id="special">Second paragraph</p>
	<p class="myParagraphs" >Third paragraph</p>
	<p class="myParagraphs" >Fourth paragraph</p>
	<p class="myParagraphs" >Fifth paragraph</p>
	<p class="myParagraphs" >Sixth paragraph</p>
</div>
<br><br>

### Attribute Selectors: 

In some cases, the traditional pseudo classes don&rsquo;t provide the nuance we would like to implement. *This is specifically relevant to styling input types*. CSS also lets us select elements by their attributes: 

#### Includes Attribute
If an element contains a certain attribute you can select it:
```css

a[target]{
	color: red;
}

```

#### Includes Attribute Value
If an element has a specific attribute value (like a link opening a new window):

```css

a[target="_blank"]{
	color: yellow;
}

```
Or a specific input type:
```css

input[type="submit"]{
	color: yellow;
}

input[type="text"]{
	color: black;
}

input[type="checkbox"]{
	border-color: red;
}

```

For a complete list, check out [W3Schools](https://www.w3schools.com/css/css_attribute_selectors.asp).

### Includes partial Attribute Value
Includes a whole word:
```css

img[alt~="nature"]{
	border-color: green;
}

```


Includes a string (like natu in nature or natural):
```css

img[alt*="natu"]{
	border-color: green;
}

```

### Additional CSS Selectors:

#### Nested: " "
Adding a space between selectors allows you to apply CSS to all children of the first element. 

This example would make all paragraph elements of the class `myClass` red:

```css

	.myClass p{
		color: red;
	}

```

#### Immediatly Nested: >
The closing caret `>` allows you to navigate a single level down. This example would apply to any paragraph element that is immediatly wrapped by `.myClass`:
```css

	.myClass > p{
		color: red;
	}

```

#### Immediatly Following: +
The `+` allows for us to select the following element. In this example our `margin-top` would apply to all paragraphs following an `h1` element:
```css

	h1 + p{
		margin-top: 1rem;
	}

```

#### All: *
The `*` allows for us to select all nested elements. In this example our `color` would apply to all elements inside a `main` element:
```css

	main *{
		color: red;
	}

```


