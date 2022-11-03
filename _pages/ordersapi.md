---
layout: default
title: Orders
permalink: /orders/project
type: pbl
---




<style>
.button {
  background-color: #e7e7e7; color: black;
  border: none;
  color: black;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}
</style>

<center><button class="button" onclick="orderinput()">Add Order</button><center>



<p id="order"></p>

<script>
import React, { useEffect, useState } from 'react'
import './App.css'
import {orders_list} from ./model_orders

  function orderinput() {
    let customer = prompt("Please enter customer name", "Customer name");
    if (customer != null) {
      document.getElementById("order").innerHTML =
      "New Customer: "+ customer;
    }
  }

function AddOrder () {
    const [orders, setOrders] = useState([])

    useEffect(() => {
        const fetchData = async () => {
            const result = await fetch("https://coolcoders.nighthawkcodescrums.gq")
            const jsonResult = result.json()

            setOrders(jsonResult)
        }

        fetchData()
    }, [])

    const submitOrder = async () => {
        const myData = {
            customer
        }

    const result = await fetch("https://coolcoders.nighthawkcodescrums.gq")
    }
}
  


</script>

<!-- HTML table fragment for page -->
<table>
  <thead>
  <tr>
    <th>Customer Name</th>
    <th>Item Purchased</th>
    <th>Quantity</th>
  </tr>
  </thead>
  <tbody id="result">
    <!-- javascript generated data -->
  </tbody>
</table>


<!-- Script is layed out in a sequence (without a function) and will execute when page is loaded -->
<script>

  // prepare HTML defined "result" container for new output
  const resultContainer = document.getElementById("result");

  // prepare fetch urls
  const url = "https://coolcoders.nighthawkcodescrums.gq/api/orders"; 
  const lower_url = url + "/quantity/";  // quantity

   // prepare fetch GET options
  const options = {
    method: 'GET', // *GET, POST, PUT, DELETE, etc.
    mode: 'cors', // no-cors, *cors, same-origin
    cache: 'default', // *default, no-cache, reload, force-cache, only-if-cached
    credentials: 'omit', // include, *same-origin, omit
    headers: {
      'Content-Type': 'application/json'
      // 'Content-Type': 'application/x-www-form-urlencoded',
    },
  };
  // prepare fetch PUT options, clones with JS Spread Operator (...)
  const put_options = {...options, method: 'PUT'}; // clones and replaces method

  // fetch the API
  fetch(url, options)
    // response is a RESTful "promise" on any successful fetch
    .then(response => {
      // check for response errors
      if (response.status !== 200) {
          error('GET API response failure: ' + response.status);
          return;
      }
      // valid response will have JSON data
      response.json().then(data => {
          console.log(data);
          for (const row of data) {
            // make "tr element" for each "row of data"
            const tr = document.createElement("tr");

            // td for item cell
            const orders = document.createElement("td");
              orders.innerHTML = row.id + ". " + row.item + row.quantity;  // add fetched data to innerHTML

            // this builds ALL td's (cells) into tr (row) element
            tr.appendChild(orders);

             // this adds all the tr (row) work above to the HTML "result" container
            resultContainer.appendChild(tr);
          }
      })
  })

  // catch fetch errors (ie Nginx ACCESS to server blocked)
  .catch(err => {
    error(err + " " + url);
  });

  // Reaction function to quantity user actions
  function subtract(type, put_url, elemID) {

    // fetch the API
    fetch(put_url, put_options)
    // response is a RESTful "promise" on any successful fetch
    .then(response => {
      // check for response errors
      if (response.status !== 200) {
          error("PUT API response failure: " + response.status)
          return;  // api failure
      }
      // valid response will have JSON data
      response.json().then(data => {
          console.log(data);
          // quantity updated/decreased
          if (type === QUANTITY) // quantity data element
            document.getElementById(elemID).innerHTML = data.quantity;  // fetched quantity data assigned to quantity Document Object Model (DOM)
          else
            error("unknown type: " + type);  // should never occur
      })
    })
    // catch fetch errors (ie Nginx ACCESS to server blocked)
    .catch(err => {
      error(err + " " + put_url);
    });
    
  }

  // Something went wrong with actions or responses
  function error(err) {
    // log as Error in console
    console.error(err);
    // append error to resultContainer
    const tr = document.createElement("tr");
    const td = document.createElement("td");
    td.innerHTML = err;
    tr.appendChild(td);
    resultContainer.appendChild(tr);
  }

</script>
