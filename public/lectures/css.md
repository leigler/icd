# CSS
<div class="presentation">
	<h2>Cascading StyleSheets</h2>
	<p>CSS is how we style and shape our HTML.</p>
</div>

<div class="presentation">
	<h2>Connecting our CSS to our HTML</h2>
	<p>In order to connect our CSS to our HTML, we use the link tag:</p>
	<p><code>&#60;link rel="stylesheet" type="text/css" href="your/path/here/style.css"></code></p>
</div>


<div class="presentation">
	<h2>Connecting our CSS to our HTML</h2>
	<img src="/files/css.jpg">
</div>

<div class="presentation">
	<h2>Connecting our CSS to our HTML</h2>
	<p>We then have several ways to <i>tell</i> our html what to look like:</p>
	<h3>A raw html element:</h3>
<pre>
<code>&#60;div>My content&#60;/div></code>
</pre>
	<pre>
<code>div {</code>
	<code>color: red;</code>
<code>}</code>
	</pre>
</div>

<div class="presentation">
	<h2>Connecting our CSS to our HTML</h2>
	<h3>...A class:</h3>
	<p>A class can be used to style multiple elements (even if they are different element types). All elements can have as many classes as you want, and each class can be used as many times as needed.</p>
<pre>
<code>&#60;div class="myClass">My content&#60;/div></code>
<code>&#60;h1 class="myClass">My h1&#60;/h1></code>
<code>&#60;a href="https://xxxi.nyc" class="myClass">My link&#60;/a></code>
</pre>
	<pre>
<code>.myClass{</code>
	<code>color: green;</code>
<code>}</code>
	</pre>
</div>
<div class="presentation">
	<h2>Connecting our CSS to our HTML</h2>
	<h3>...An Id:</h3>
	<p>An id overrides both element and class style. Each Id is can be used only once:</p>
<pre>
<code>&#60;div class="myClass" id="myId">My content&#60;/div></code>
</pre>
	<pre>
<code>#myId{</code>
	<code>color: blue;</code>
<code>}</code>
	</pre>
</div>

<div class="presentation">
	<p>Let&rsquo;s try it out!</p>
	<p>Download the <a href="/files/boilerplate.zip">Boilerplate</a></p>
</div>


*** 
## Box Model
Each html element has a margin, border, and padding:

<div
	style="
	width: 300px;
	height: 200px;
	background-color: #FCA31D;
	margin: 20px;
	padding: 15px;
	border: solid 10px #FC1D95;
	"
>	<code>width: 300px;</code><br><br>
	<code>height: 200px;</code><br><br>
	<code>margin: 20px;</code><br><br>
	<code>padding: 5px;</code><br><br>
	<code>border-width: 10px;</code>
</div>

<div
	style="
	width: 300px;
	height: 200px;
	background-color: #FCA31D;
	margin: 20px;
	padding: 15px;
	border: solid 10px #FC1D95;
	box-sizing: border-box;
	overflow: hidden;
	"
> 
	<code>width: 300px;</code><br><br>
	<code>height: 200px;</code><br><br>
	<code>box-sizing: border-box;</code><br><br>	
	<code>margin: 20px;</code><br><br>
	<code>padding: 5px;</code><br><br>
	<code>border-width: 10px;</code>
</div>

You can either use these to expand the element&rsquo;s size, or you may use `box-sizing: border-box;` to limit the height and width of an element.

## Units
CSS Units include: 
- `px` defines a pixel unit (not responsive)
- `%` defines the size in relation to its parent
- `vw` defines size in relation to browser width
- `vh` defines size in relation to browser height
- `rem` is a custom unit that is defined by the `font-size` in the `html` tag


## Relative
HTML positions all elements as `relative`, with almost all elements also displaying at the `block` level. This means they &ldquo;naturally&rdquo; flow in a column:
<br><br>
<div style="width: 100%; height: 40px; background-color: #FC1D95;"></div>
<div style="width: 100%; height: 40px; background-color: #00F2B8;"></div>
<div style="width: 100%; height: 40px; background-color: #FCA31D;"></div>
<br>
<div style="width: 100px; height: 40px; background-color: #FC1D95;"></div>
<div style="width: 100px; height: 40px; background-color: #00F2B8;"></div>
<div style="width: 100px; height: 40px; background-color: #FCA31D;"></div>
<br>When maintaining the `position: relative;`, elements can also be stacked side-by-side with `display: inline-block;`:
<br><br>
<div style="display:inline-block; width: 100px; height: 40px; background-color: #FC1D95;"></div>
<div style="display:inline-block; width: 100px; height: 40px; background-color: #00F2B8;"></div>
<div style="display:inline-block; width: 100px; height: 40px; background-color: #FCA31D;"></div>

<br>The tiny space between elements is due the the hard return in the html: 

```html

<div class="sideBySide"></div>
<div class="sideBySide"></div>
<div class="sideBySide"></div>

```

This can be solved by removing the space between the actual html elements: 

```html

<div class="sideBySide"></div
><div class="sideBySide"></div
><div class="sideBySide"></div>

```

<br>To produce: 
<br><br>
<div style="display:inline-block; width: 100px; height: 40px; background-color: #FC1D95;"></div
	><div style="display:inline-block; width: 100px; height: 40px; background-color: #00F2B8;"></div
	><div style="display:inline-block; width: 100px; height: 40px; background-color: #FCA31D;"></div
	>
<br>

<br>These elements can then take on a responsive percentage: 

<br>
<div style="display:inline-block; width: 33.33%; height: 40px; background-color: #FC1D95;"></div
	><div style="display:inline-block; width: 33.33%; height: 40px; background-color: #00F2B8;"></div
	><div style="display:inline-block; width: 33.33%; height: 40px; background-color: #FCA31D;"></div
	>
<br>

<br>In case of unequal height, you can use the css attribute `vertical-align: top;` (or `middle`, or `bottom`): to change the element&rsquo;s alignment: 
<br><br>
<div style="display:inline-block; vertical-align: top; width: 33.33%; height: 100px; background-color: #FC1D95;"></div
	><div style="display:inline-block; vertical-align: top; width: 33.33%; height: 40px; background-color: #00F2B8;"></div
	><div style="display:inline-block; vertical-align: top; width: 33.33%; height: 200px; background-color: #FCA31D;"></div
	>
<br>
<br>
<div style="display:inline-block; vertical-align: middle; width: 33.33%; height: 100px; background-color: #FC1D95;"></div
	><div style="display:inline-block; vertical-align: middle; width: 33.33%; height: 40px; background-color: #00F2B8;"></div
	><div style="display:inline-block; vertical-align: middle; width: 33.33%; height: 200px; background-color: #FCA31D;"></div
	>
<br>
<br>
<div style="display:inline-block; vertical-align: bottom; width: 33.33%; height: 100px; background-color: #FC1D95;"></div
	><div style="display:inline-block; vertical-align: bottom; width: 33.33%; height: 40px; background-color: #00F2B8;"></div
	><div style="display:inline-block; vertical-align: bottom; width: 33.33%; height: 200px; background-color: #FCA31D;"></div
	>
<br><br>



## Absolute

Elements can also be given positions of absolute (in which case they are removed from the relatively positioned cascade. These elements can now utilize the `left`, `top`, `right`, and `bottom` properties: 

<div style="
position: absolute;
padding: 20px;
height: 100px;
left: 40%;
background-color: #FCA31D;
"><code>position: absolute;</code><br><br><code>left: 50%;</code></div>

<div id="hidden_absolute" style="
position: absolute;
padding: 20px;
top: 940vh;
right: 20%;
display: none;
background-color: #FC1D95;;
"><code>position: absolute;</code><br><br><code>left: 20%;</code>
<br><br><code>top: 20%;</code></div>

<button class="special_button" onClick="document.getElementById('hidden_absolute').style.display = 'block'; ">Show absolute Div</button>


<br><br><br><br>`absolute` positioned elements are directly related to their parent element when their parent&rsquo;s position is clearly defined: 

<div
	style=" position: relative; width: 40%; height: 300px; background-color: #00F2B8;"
>
	<div style="position: absolute; top: 160px; left: 50px; height: 50px; padding: 20px; background-color: #FCA31D;">this is the child element</div>
</div>

<br>The css:
```css

	#parent{
		position: relative; 
		width: 40%; 
		height: 300px; 
		background-color: #00F2B8;
		overflow: hidden;
	}

	#child{
		position: absolute; 
		top: 160px; 
		left: 50px; 
		height: 50px; 
		padding: 20px; 
		background-color: #FCA31D;
	}
	

```

## Transform
CSS also allows you to manipulate how individual elements look regardless of their position via the `transform` property ([more here](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)):
<br><br>
<div style="
	display: inline-block;
	width: 100px;
	height: 100px;
	background-color: #FC1D95;

"></div>
<div style="
	display: inline-block;
	width: 100px;
	height: 100px;
	background-color: #00F2B8;
	transform: rotate(35deg);

"></div>
<div style="
	display: inline-block;
	width: 100px;
	height: 100px;
	background-color: #FCA31D;
	transform: skew(35deg);

"></div>
