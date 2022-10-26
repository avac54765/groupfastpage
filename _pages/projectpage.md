---
layout: default
title: Merchandise User Project
permalink: /merch/project
type: pbl
---

<!-- from w3schools-->

<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
    body, html {
     height: 100%;
    }
    .parallax {
     /* The image used */
    background-image: url('/images/delnorte.jpg');
    /* Full height */
    height: 100%; 
    /* Create the parallax scrolling effect */
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    }
</style>
</head>
    <body>

<div class="parallax"></div>

<div style="height:1000px;background-color:grey;font-size:36px">


<!-- Trigger/Open The Modal -->
 <button id="myBtn">Draft Email to Customer</button>

 <!-- The Modal -->
 <div id="myModal" class="modal">

<!-- Modal content -->
 <div class="modal-content">
        <span class="close">&times;</span>
        <p>Hello __(customer name here)__!
            Thank you so much for your order! Please come to the student store at lunch to pick up your new swaggy merchandise!
        Sincerely,
        __Merch Andise__(commissioner name)
        Del Norte ASB
        Merchandise Commmissioner</p>
    </div>

</div>

<script>
// Get the modal
var modal = document.getElementById("myModal");

// Get the button that opens the modal
var btn = document.getElementById("myBtn");

// Get the <span> element that closes the modal
var span = document.getElementsByClassName("close")[0];

// When the user clicks the button, open the modal 
btn.onclick = function() {
  modal.style.display = "block";
}

// When the user clicks on <span> (x), close the modal
span.onclick = function() {
  modal.style.display = "none";
}

// When the user clicks anywhere outside of the modal, close it
window.onclick = function(event) {
  if (event.target == modal) {
    modal.style.display = "none";
  }
}
</script>
</html>
</div>

<div class="parallax"></div>

</body>
</html>