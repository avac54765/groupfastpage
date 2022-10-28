---
layout: default
title: Contact
permalink: /merch/project
type: pbl
---




<!-- Starting Over code without Parallax-->
<!-- info from w3schools-->

<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
.button {
  padding: 15px 25px;
  font-size: 24px;
  text-align: center;
  cursor: pointer;
  outline: none;
  color: #fff;
  background-color: ##FFFAF0;
  border: none;
  border-radius: 15px;
  box-shadow: 0 9px #999;
}
.button:hover {background-color: #DCDCDC}
.button:active {
  background-color: #DCDCDC;
  box-shadow: 0 5px #666;
  transform: translateY(4px);
}
.modal {
  position: absolute;
  top: 0;
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
</head>
<body>

<button class="button" style="margin-left: auto; margin-right: auto;" onclick="alert('Email content here')">Email Draft</button>
    <div class="modal">
      <div class="modal_contents">
        <p>Email content here</p>
      </div> 
    </div>
</body>   

</html>



<!-- code with parallax-->
<!-- from w3schools-->

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

    <div style="height:200px;background-color:#696969;font-size:20px">

<!--Trigger/Open The Modal -->
        <button id="myBtn"><center>Draft Email to Customer</center></button>

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
</div>

<div class="parallax"></div>

</body>
</html>