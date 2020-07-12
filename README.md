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

  // If we need to apply some CSS, we can quickly do so, using the jQuery ".attr" method.
  newDiv.attr("class", "insertClassNameHere");
```

## Generating content from Arrays
``` javascript
  var drinkList = [
    "Coffee: $5",
    "Espresso: $7",
    "Cappuccino: $6"
  ];

  // This line of jQuery selects the div with the matching id (#drink-options)
  var drinkDiv = $("#drink-options");

  // Here we use jQuery's custom .each method to loop through the object and immediately create divs.
  $.each(drinkList, function(number, drink){
    drinkDiv.append("<div>" + drink + "</div>")
  });

```

## OnClick
```javascript
// This "document.ready" code isn't necessary in this example... but is useful to become familiar with.
    // "document.ready" makes sure that our JavaScript doesn't get run until the HTML document is finished loading.
    $(document).ready(function() {

      // Here we use jQuery to select the header with "click-me" as its ID.
      // Whenever it is clicked...
      $("#click-me").on("click", function() {

        // ... we trigger an alert.
        alert("I've been clicked!");
      });

    });
```

## Generate a random number
```javascript
$("#random-button").on("click", function() {

        // Create a string which will hold the lottery number
        var lottoNumber = "";

        // Then initiate a loop to generate 9 separate numbers
        for (var i = 0; i < 9; i++) {

          // For each iteration, generate a new random number between 1 and 9.
          var random = Math.floor(Math.random() * 9) + 1;

          // Take this number and then add it to the rest of the string.
          // In essence, we are iteratively building a string of numbers. (e.g. First: 1, Second: 13, Third: 135, etc.)
          lottoNumber = random + lottoNumber;

        }

        // Once we have our final lotto number, we'll prepend it to the top of our random-number div.
        $("#random-number").prepend("<br><hr>" + lottoNumber);
      });
```
