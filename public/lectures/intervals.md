## Intervals

Javascript also allows us to run actions with delay or on repeat:

### Delay (setTimeout)
Javascript uses milliseconds rather than seconds, so `1000` = 1 second.

```javascript

setTimeout(function(){
	console.log("this was delayed!")
}, 1000)

```

### Repeat (setInterval)
```javascript

setInterval(function(){
	console.log("this will repeat every second!")
}, 1000)

```

You can use the setInterval to update a variable outside of it:

```javascript

var myNumber = 0;

setInterval(function(){
	console.log(myNumber)
	myNumber = myNumber + 1;

}, 1000)

```

#### Stopping your Interval

To stop an interval, you have to save it as a variable and then use `clearInterval()`:

```javascript 

var myNumber = 0;

var myTimer = setInterval(function(){
	myNumber = myNumber + 1;

	console.log(myNumber)

	if(myNumber > 10){
		clearInterval(myTimer);
		alert("party is over!", myNumber)
	}

}, 1000)




```