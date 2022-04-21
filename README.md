# WEBLAB5
Task # 01: Using the Shopping List files from the previous videos update the shopping list app to do the following:

A. If you click on the list item, it toggles the .done  class on and off.

B. Add buttons next to each list item to delete the item when clicked on its corresponding delete button.

C. BONUS: When adding a new list item, it automatically adds the delete button next to it (hint: be sure to check if new items are clickable too!)


CODE:
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body {
  margin: 0;
  min-width: 250px;
}

* {
  box-sizing: border-box;
}

ul {
  margin: 0;
  padding: 0;
}

ul li {
  cursor: pointer;
  position: relative;
  padding: 12px 8px 12px 40px;
  list-style-type: none;
  background: #eee;
  font-size: 18px;
  transition: 0.2s;
  
  
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

ul li:nth-child(odd) {
  background: #f9f9f9;
}

ul li:hover {
  background: #ddd;
}

ul li.checked {
  background: #888;
  color: #fff;
  text-decoration: line-through;
}

ul li.checked::before {
  content: '';
  position: absolute;
  border-color: #fff;
  border-style: solid;
  border-width: 0 2px 2px 0;
  top: 10px;
  left: 16px;
  transform: rotate(45deg);
  height: 15px;
  width: 7px;
}

.close {
  position: absolute;
  right: 0;
  top: 0;
  padding: 12px 16px 12px 16px;
}

.close:hover {
  background-color: #f44336;
  color: white;
}

.header {
  background-color: #f44336;
  padding: 30px 40px;
  color: white;
  text-align: center;
}

.header:after {
  content: "";
  display: table;
  clear: both;
}

input {
  margin: 0;
  border: none;
  border-radius: 0;
  width: 75%;
  padding: 10px;
  float: left;
  font-size: 16px;
}

.addBtn {
  padding: 10px;
  width: 25%;
  background: #d9d9d9;
  color: #555;
  float: left;
  text-align: center;
  font-size: 16px;
  cursor: pointer;
  transition: 0.3s;
  border-radius: 0;
}

.addBtn:hover {
  background-color: #bbb;
}
</style>
</head>
<body>

<div id="myDiv" class="header">
  <h2 style="margin:5px">My To Do List</h2>
  <input type="text" id="myInput" placeholder="Title...">
  <span onclick="newElement()" class="addBtn">Add</span>
</div>

<ul id="myUl">
  <li>Hit the gym</li>
  <li class="checked">Pay bills</li>
  <li>Meet George</li>
  <li>Buy eggs</li>
  <li>Read a book</li>
  <li>Organize office</li>
</ul>

<script>

var myNodelist = document.getElementsByTagName("LI");
var i;
for (i = 0; i < myNodelist.length; i++) {
  var span = document.createElement("SPAN");
  var txt = document.createTextNode("\u00D7");
  span.className = "close";
  span.appendChild(txt);
  myNodelist[i].appendChild(span);
}

var close = document.getElementsByClassName("close");
var i;
for (i = 0; i < close.length; i++) {
  close[i].onclick = function() {
    var div = this.parentElement;
    div.style.display = "none";
  }
}

var list = document.querySelector('ul');
list.addEventListener('click', function(ev) {
  if (ev.target.tagName === 'LI') {
    ev.target.classList.toggle('checked');
  }
}, false);

// Create a new list item when clicking on the "Add" button
function newElement() {
  var li = document.createElement("li");
  var inputValue = document.getElementById("myInput").value;
  var t = document.createTextNode(inputValue);
  li.appendChild(t);
  if (inputValue === '') {
    alert("You must write something!");
  } else {
    document.getElementById("myUl").appendChild(li);
  }
  document.getElementById("myInput").value = "";

  var span = document.createElement("SPAN");
  var txt = document.createTextNode("\u00D7");
  span.className = "close";
  span.appendChild(txt);
  li.appendChild(span);

  for (i = 0; i < close.length; i++) {
    close[i].onclick = function() {
      var div = this.parentElement;
      div.style.display = "none";
    }
  }
}
</script>

</body>
</html>

Task # 02: Write a JavaScript program to calculate the volume of a sphere.
 
CODE:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Volume Of Sphere</title>
</head>
<body >
    <h2 style="text-align: center; color: rgb(183, 0, 255); font-family: 'Franklin Gothic Medium';">Input radius value and get the volume of sphere</h2>
    <br>
    <form style="text-align: center;">
        <h3 style="color: rgb(255, 0, 212);">Radius</h3>
        <input type = number id="Rad" name="rad">
        <h3 style="color:  rgb(255, 0, 212);">Volume</h3>
        <input type = number id="vol" name="vol">
        <br>
        <button type="button" id="btn" style="background-color: aqua;">Calculate Volume</button>
    </form>
    <script type="text/javascript">
function calculateVolume() {
let radius = document.getElementById("Rad").value;
let volume = 4/3*Math.PI*Math.pow(radius,3);
document.getElementById("vol").value = volume.toFixed(2);
}
let button = document.getElementById("btn");
button.onclick = calculateVolume;

    </script>
</body>
</html>
OUTPUT:
 

  CODE:
<!doctype html>
<html lang="en">
  <head>
   
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
    
    <link href="../assets/dist/css/bootstrap.min.css" rel="stylesheet">
    
     </head>

  <body>

      <br>
      <h2 class="text-center">TASK 3</h2>
    <div class="container" style="background-color: indigo; ">
        <div class="row">
          <div class="col-12">
            <table class="table table-bordered">
              <thead>
                <tr>
                  <th scope="col" style="color:white">Select any one option:</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td scope="row"><button type="button" onclick="generateTable()" class="btn btn-outline-light">Generate table</button></td>
                
                </tr>
                <tr>
                    <td scope="row"><button type="button" onclick="calculatePower()" class="btn btn-outline-light">Calculate Power</button></td>
                  </tr>
                  <tr>
                    <td scope="row"><button type="button" onclick="generateSeries()" class="btn btn-outline-light">Generate Series</button></td>
                    
                  </tr>
                  <tr>
                    <td scope="row"><button type="button" onclick="generateEvenOdd()" class="btn btn-outline-light">Generate odd No./Even No.</button></td>
                  </tr>
                
              </tbody>
            </table>
          </div>
        </div>
      </div>
      <br>
      
</body>
<script type="text/javascript">
function generateTable () {
    
    var number = prompt("Please enter a number:");
    document.write('<table border="1">');
    for (i=1; i <= 12; i++) {
        document.write('<tr><td>' + number + " x " + i + "</td><td>=</td><td>" + i*number + "</td></tr>");
    };
    document.write('</table>');
}
function calculatePower () {
    
    
    var base = prompt("Please enter a base: ");
    var power = prompt("Please enter a power: ");

    let x = Math.pow(base, power);
    document.write("The result is: "+x);
}
function generateSeries () {
    
    var start = prompt("Please enter a start: ");
    var end = prompt("Please enter a end: ");
    
    for (i=start; i <= end; i++) {
       
        document.write( i +"," +" " );
    };
}

    function generateEvenOdd () {
    
   
    var response=prompt("Enter E for even series/ O for Odd series");
    var end = prompt("Please enter a limit: ");
    
    if (response=="E") {
 for (i=2; i <= end; i=i+2) {
       
        document.write( i +" ");

    }
} else if (response=="O") {
    for (i=1; i <= end; i=i+2) {
       
       document.write( i  +" ");

   }
}
//task4
function chBackcolor(color) {
   document.button.style.background = color;
}
window.setTimeout("chBackColor()",10000);
    }

    </script>
<script src="../assets/dist/js/bootstrap.bundle.min.js"></script>  
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
       </html>

 
 
 
Task # 04: 
Create a document with multiple tabs with the background color. Upon hover background color of the document is changed accordingly
 
CODE:
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta charset="utf-8">
<style>
button{
  border: 2px solid black;
  border-radius: 5px;
}
</style>
  
</head>
<body style=" top:0px; left:0px;background-color: rgba(247, 107, 83, 0.979);">
  

    <ul class="nav nav-pills"  >
      <button type="button" id="btn1"class="btn btn-lrg" style="height: 50px; width: 50px; margin-left: 30px;">H</button>
      <button type="button" id="btn2"class="btn btn-lrg" style="height: 50px; width: 50px; ">G</button>
      <button type="button" id="btn3" class="btn btn-lrg" style="height: 50px; width: 50px; ">I</button>
      <button type="button" id="btn4" class="btn btn-lrg" style="height: 50px; width: 50px; ">P</button>
      <button type="button" id="btn5"class="btn btn-lrg" style="height: 50px; width: 50px; ">L</button>  
    </ul>
</body>
  

    <script type="text/javascript">
const btn1 = document.getElementById("btn1");
      btn1.addEventListener("mouseover", function () {
        btn1.style.backgroundColor = "orange";
 });

 const btn2 = document.getElementById("btn2");
 btn2.addEventListener("mouseover", function () {
  btn2.style.backgroundColor = "red";
 });

 const btn3 = document.getElementById("btn3");
      btn3.addEventListener("mouseover", function () {
        btn3.style.backgroundColor = "green";
 });

 const btn4 = document.getElementById("btn4");
      btn4.addEventListener("mouseover", function () {
        btn4.style.backgroundColor = "powderblue";
 });
 const btn5 = document.getElementById("btn5");
      btn5.addEventListener("mouseover", function () {
        btn5.style.backgroundColor = "plum";
 });

      
</script>
</html>



