# New York Commercial Vehicle Typography

- [TruckLife are.na channel](https://www.are.na/ben-ross-1515211424/trucklife)


## Context

New York City is filled with commercial vehicles (trucks)—containers transporting anything from food and tools to money and trash. By law, all trucks need to include some information: 

> &ldquo;The New York City Traffic Rules require that commercial vehicles display the registrant&rsquo;s name and address on both sides of the vehicle.&rdquo; <br>—([nyc.gov](https://www1.nyc.gov/html/dot/downloads/pdf/truck-and-commercial-vehicle-faq-05-2019.pdf)). 

It does not, however, say *how* this material should be displayed. This fact, along with an abundance of creativity (and often, a sense of humor) means that almost no two trucks in NYC look alike. 

## Assignment
For this first assignment, you will create two html pages. They must somehow link to one another:
- *Page One*: Embed your selected truck&rsquo;s image within an html page
- *Page Two*: Select your truck&rsquo;s broadest face (either from the are.na channel or a truck you happened to have photographed) and recreate it within the browser. Consider all elements of the truck (doors, reflective tape, large dents) and how you might translate them into css. You may use custom illustrations and open-source typefaces to create your truck page.

*When doing this assignment, I&rsquo;d recommend working from broad strokes to fine details: Block out the basic layout of your truck, working your way in to each &ldquo;component&rdquo;.*


### Best Practices
- To keep your webpage fluid, try and use percentage (`%`) and view width (`vw`) units for width-based dimensions when possible.
- Try and rely on `position: relative;` whenever possible. as a last resort, you may use `position: absolute;`
- Recognize which areas of your truck are similarly styled. Can they share a `class`?

## Additional Notes

### Resources
- [Getting to know HTML](https://learn.shayhowe.com/html-css/getting-to-know-html/)
- [Learn Layout](http://learnlayout.com/)
- [Google Fonts](https://fonts.google.com/)

### Importing Fonts

To import a font, you will want to either use a `.woff`, `.ttf`, or `.eot` file and use `@font-face`:

```css

@font-face {
  font-family: "Open Sans";
  src: url("/fonts/OpenSans-Regular-webfont.woff2") format("woff2"),
       url("/fonts/OpenSans-Regular-webfont.woff") format("woff");
}

```
<br>You may then reference your font with how you&rsquo;ve named it via the `font-family` (in this case: `"Open Sans"`). Alternative methods are often provided by online font foundries like [Google Fonts](https://fonts.google.com)
