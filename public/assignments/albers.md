# Josef Albers

Take a moment to acquaint yourself with this pdf of the book [&ldquo;Interaction of Color&rdquo;](http://www.g-e-s-t-a-l-t.org/MEDIA/PDF/Interaction-of-Color.pdf) by Josef Albers.

Using your knowledge of interactive (and potentially logic-based) [pseudo-classes](/lectures/csspseudo), select an example from this book and create an interactive version of it with HTML and CSS. 

Consider what elements of the composition you can nest to keep transitions smooth. Additionally, consider whether elements should be written as `input` or `button` to take advantage of `focus` states.

## An example
(not relating to any specific Albers composition)

<style type="text/css">
	
	input, button{
		-webkit-appearance: none;
		-moz-appearance: none;
		outline: none;
	}

	button{
		margin: 0.25rem;
		margin-bottom: 2rem;
		vertical-align: top;
		display: inline-block;
		width: 20rem;
		height: 20rem;
		border: none;
		background-color: #FC1D95;
		border-radius: 5px;
		transition: background-color 0.5s;
		cursor: pointer;
	}

	input.nested{
		border: none;
		background-color:#FCA31D;
		transition: background-color 0.5s;
		width: 10rem;
		height: 10rem;
	}

	button:hover{
		background-color:#FCA31D;
	}

	button:hover input.nested{
		background-color: #FC1D95;
	}

	button:focus, input:focus, button:hover input:focus{
		background-color: #00F2B8;
	}

</style>

<button><input type="submit" value="" class="nested"></input></button>
<button><input type="submit" value="" class="nested"></input></button>


```css

input, button{
	-webkit-appearance: none;
	-moz-appearance: none;
	outline: none;
}

button{
	margin: 0.25rem;
	margin-bottom: 2rem;
	vertical-align: top;
	display: inline-block;
	width: 20rem;
	height: 20rem;
	border: none;
	background-color: #FC1D95;
	border-radius: 5px;
	transition: background-color 0.5s;
	cursor: pointer;
}

input.nested{
	border: none;
	background-color:#FCA31D;
	transition: background-color 0.5s;
	width: 10rem;
	height: 10rem;
}

button:hover{
	background-color:#FCA31D;
}

button:hover input.nested{
	background-color: #FC1D95;
}

button:focus, input:focus, button:hover input:focus{
	background-color: #00F2B8;
}


```
