---
layout: default
title: Stock
permalink: /stock/project
type: pbl
---


<!-- HTML table fragment for page -->
<table>
  <thead>
  <tr>
    <th>Merchandise Item</th>
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

  // keys for joke reactions
  const QUANTITY = stock_data[id]['quantity'];


  // prepare fetch urls
  const url = "https://coolcoders.nighthawkcodescrums.gq/api/stocks"; 
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
            const stock = document.createElement("td");
              stock.innerHTML = row.id + ". " + row.item;  // add fetched data to innerHTML

            // td for quantity cell with onclick actions
            const quantity = document.createElement("td");
              const quantity_but = document.createElement('button');
              quantity_but.id = QUANTITY+row.id   // establishes a quantity JS id for cell
              quantity_but.innerHTML = row.quantity;  // add fetched "quantity count" to innerHTML
              quantity_but.onclick = function () {
                // onclick function call with "quantity parameters"
                reaction(QUANTITY, lower_url+row.id, quantity_but.id);  
              };
              quantity.appendChild(quantity_but);  // add "quantity button" to quantity cell

            // this builds ALL td's (cells) into tr (row) element
            tr.appendChild(stock);
            tr.appendChild(quantity);

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
  function reaction(type, put_url, elemID) {

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
          if (type === quantity) // quantity data element
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
