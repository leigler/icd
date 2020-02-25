# CSS Part 2
## CSS Animations
Within CSS, you can assign looping animations to elements using the `@keyframes` at-rule:

```css

@keyframes myAnimation{

	from{
		font-size: 20px;
	}

	to{
		font-size: 40px;
	}

}


.myTitle{
	font-size: 20px;
	animation-name: myAnimation;
	animation-duration: 4s;
	animation-fill-mode: forwards;
}


```
<style type="text/css">
@keyframes myAnimation{
	from{
		font-size: 20px;
	}
	to{
		font-size: 40px;
	}
}

.myTitle{
	font-size: 20px;
	animation-name: myAnimation;
	animation-duration: 10s;
	animation-fill-mode: forwards;
}
</style>

<div class="myTitle">my Title!</div>

Of course you can exercise quite a bit more nuance using percentages:

```css

@keyframes myOtherAnimation{

	0%{
		font-size: 20px;
	}

	20%{
		font-size: 40px;
	}

	40%{
		font-size: 20px;
	}

	60%{
		font-size: 100px;
	}

	80%{
		font-size: 10px;
	}

	100%{
		font-size: 120px;
	}

}


#mySecondTitle{
	font-size: 20px;
	animation-name: myOtherAnimation;
	animation-duration: 4s;
	animation-fill-mode: forwards;
}

#myThirdTitle{
	font-size: 20px;
	animation-name: myOtherAnimation;
	animation-duration: 8s;
	animation-fill-mode: forwards;
}


```

<style type="text/css">
	
	@keyframes myOtherAnimation{

	0%{
		font-size: 20px;
	}

	20%{
		font-size: 40px;
	}

	40%{
		font-size: 20px;
	}

	60%{
		font-size: 100px;
	}

	80%{
		font-size: 10px;
	}

	100%{
		font-size: 120px;
	}

}


#mySecondTitle{
	font-size: 20px;
	animation-name: myOtherAnimation;
	animation-duration: 4s;
}

#myThirdTitle{
	font-size: 20px;
	animation-name: myOtherAnimation;
	animation-duration: 8s;
}
</style>

<div id="mySecondTitle">my second Title!</div>
<div id="myThirdTitle">my third Title!</div>


<br><br>
## Detailing
Other than the explicit states, almost everything else is determined by the class or id you assign the animation to—this is quite practical as it means you can re-use the same animation with some variation:

```css
@keyframes spinning{
	0%{
		transform: rotate(0deg);
	}

	100%{
		transform: rotate(360deg);
	}
}

.square, .circle{
	display: inline-block;
	margin-right: 2rem;
}

.square{
	width: 2rem;
	height: 2rem;
	background-color: red;
	animation-name: spinning;
	animation-delay: 2s;
	animation-duration: 4s;
	animation-direction: alternate-reverse;
	animation-iteration-count: infinite;
	animation-timing-function: linear;
}

.circle{
	width: 2rem;
	height: 2rem;
	background-color: red;
	border-radius: 0.3rem;
	animation-name: spinning;
	animation-delay: 2s;
	animation-duration: 2s;
	animation-iteration-count: 10;
	animation-timing-function: ease-in-out;
}

```

<style type="text/css">
	
	@keyframes spinning{
		0%{
			transform: rotate(0deg);
		}

		100%{
			transform: rotate(360deg);
		}
	}

	.square, .circle{
		display: inline-block;
		margin-right: 2rem;
		width: 5rem;
		height: 5rem;
	}

	.square{
		background-color: red;
		animation-name: spinning;
		animation-delay: 2s;
		animation-duration: 4s;
		animation-direction: alternate-reverse;
		animation-iteration-count: infinite;
		animation-timing-function: linear;
	}

	.circle{
		background-color: red;
		border-radius: 0.3rem;
		animation-name: spinning;
		animation-delay: 2s;
		animation-duration: 2s;
		animation-iteration-count: 10;
		animation-timing-function: ease-in-out;
	}
</style>

<div class="square"></div>
<div class="circle"></div>


## Hover
You can even assign an animation on hover!
<style type="text/css">
	
	.hovering-animation{
		display: inline-block;
		margin-right: 2rem;
		width: 5rem;
		height: 5rem;
		background-color: blue;
		vertical-align: top;
		box-sizing: border-box;
		padding: 0.5rem;
		color: white;
		text-align: center;
	}

	.alt{
		animation-name: spinning;
		animation-duration: 2s;
		animation-iteration-count: infinite;
		animation-timing-function: linear;
		color: white;
	}

	.hovering-animation:not(.alt):hover{
		animation-name: spinning;
		animation-duration: 1s;
	}

	.hovering-animation.alt:hover{
		animation-direction: reverse;	
	}




</style>

<div class="hovering-animation"></div>
<div class="hovering-animation alt">alternate direction</div>

```css

.alt{
	animation-name: spinning;
	animation-duration: 2s;
	animation-iteration-count: infinite;
	animation-timing-function: linear;
}

.hovering-animation:not(.alt):hover{
	animation-name: spinning;
	animation-duration: 1s;
}

.hovering-animation.alt:hover{
	animation-direction: reverse;	
}


```




