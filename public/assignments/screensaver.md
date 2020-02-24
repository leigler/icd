# Screensaver

The past few weeks we&rsquo;ve been using CSS and HTML to recreate static graphics to get our footing in laying out complex webpages. For next week, we want to push the limits of CSS and HTML on two additional fronts: interaction and animation.

Using your knowledge so far, create an animated, interactive and fully responsive screensaver. 

## Recommendations
- Try and combine [pseudo-classes](/lectures/csspseudo)—how might you implement hover effects that alternate or appear random?
- Rather than sketching before, try and immediatly jump into your text editing app and see what forms you are able to generate.
- Don&rsquo;t be afraid to next elements. Especially when utilizing CSS hover and active states, nesting allows you to produce complex interactive [results](https://terrychen01.github.io/interactive2/exercise-hover/index.html).


## *Bonus*
Add a media query that restyles your screensaver and allows you to print at any point!

## Default HTML Interactive elements and how to override them
HTML is filled with default [input types](https://www.w3schools.com/howto/howto_js_rangeslider.asp) interactive elements (buttons, links, text input forms).

### Some important CSS attributes for overriding default styles:
```css

input{
	border: none; /* gets rid of border */
	border-radius: none; /* removes curved corners */
	outline: 0; /* removes blue outline on select */
	background-color: transparent; 
	/* defines background color away from default */
	-webkit-appearance: none; /* gets rid of default inherited styles */
	-moz-appearance: none; /* same thing but for Mozilla browsers */
}

```

### Override examples:
- [Custom Slider CSS](https://www.w3schools.com/howto/howto_js_rangeslider.asp)
- [Custom Checkbox](https://www.w3schools.com/howto/tryit.asp?filename=tryhow_css_custom_checkbox)



## References
- Vera Molnár&rsquo;s [Prints](https://www.are.na/daniel-lefcourt/monograph-vera-molnar)
- [clickclickclick.click](https://clickclickclick.click/)
- O-R-G&rsquo;s [Screensavers](http://www.o-r-g.com/screensavers) + and [Interview](https://walkerart.org/magazine/meet-the-tetracono)
- [Websites](https://www.newrafael.com/websites/) by Rafael Rozendall
- [Terry Chen&rsquo;s Hover explorations](https://terrychen01.github.io/interactive2/exercise-hover/index.html)
- Mindy Seu&rsquo;s essay on [The Poetry of Tools](https://www.are.na/blog/the-poetry-of-tools)
