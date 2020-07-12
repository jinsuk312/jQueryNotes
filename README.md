# jQueryNotes
jQuery Notes, will be continuously added to.
## Get CDN or Install
Get it here from https://code.jquery.com/ or https://developers.google.com/speed/libraries
```javascript
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
```
add script and insert in <head>
  
## Display array contents on page.

```javascript
var drinks = [
  "Coffee: $5",
  "Espresso: $7",
  "Cappuccino: $6",
  "Latte: $4"
];

var drinkDiv = document.getElementById("main");
for (var i = 0; i < drinks.length; i++) {
  // For each drink in the array, we create a new placeholder div.
  // This placeholder will get overwritten with each iteration of the loop.
  var newDrinkDiv = document.createElement("div");
  // We then assign the the value of this placeholder div to be the text in the array.
  newDrinkDiv.innerHTML = drinks[i];
  // We then add the placeholder div to the our main div on the page ("#drink-options")
  drinkDiv.appendChild(newDrinkDiv);
}
```

## Select & Append
```javascript
// .HTML method to select and change the contents of our empty-div.
    $("#empty-div").html("<h1>Hello friends!</h1>");

    // Append to a new line using .append method.
    $("#empty-div").append("A pleasure to meet you!");
    
    // If we needed each line to be its own div, we could just as easily create a new div.
    var newDiv = $("<div>");
    newDiv.html("A pleasure to meet you!");

    // We can then  append it to the other div using the same ".append" method.
    $("#empty-div").append(newDiv);
    
    var newDiv = $("<div>");
    newDiv.html("A pleasure to meet you!");

    $("#empty-div").append(newDiv);

    // If we need to apply some CSS, we can quickly do so, using the jQuery ".attr" method.
    newDiv.attr("class", "fancy");
```
