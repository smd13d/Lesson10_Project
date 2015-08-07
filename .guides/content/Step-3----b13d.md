<center><h2>Asynchronous HTTP Request</h2></center>

<ol>
<li>In your browser, review the jQuery AJAX Method: <code>$ajax()</code> [http://www.w3schools.com/jquery/ajax_ajax.asp](http://www.w3schools.com/jquery/ajax_ajax.asp).
</li>
<ul>
<li>
  <b>ajax() Usage:</b><br>
--The ajax() method is used to perform an AJAX (asynchronous HTTP) request.

--All jQuery AJAX methods use the ajax() method. This method is mostly used for requests where the other methods cannot be used.
</li>
</ul>
<li>
Parameters used in this application:
<ul>
<li><b>type</b> - Specifies the type of request. (GET or POST)</li>
<li><b>url:</b> - Specifies the URL to send the request to. Default is the current page</li>
<li><b>data:</b> - Specifies data to be sent to the server</li>
<li><b>dataType:</b> - The data type expected of the server response</li>
</ul>
</li>
<li>
The following code in the <code>search.html</code> file, <code>$(':submit').click(function(){</code> is a click event which occurs when an submit button is clicked.  The click() method triggers the the function to run when a click event occurs.
</li>
<li>
The following code in the <code>search.html</code> file, <code>var message = 'q=' + document.getElementsByTagName("input")[0].value;</code> is responsible for capturing the search request the user types in the input field.
</li>
<li>
Add the following code AFTER <code>var message = 'q=' + document.getElementsByTagName("input")[0].value;</code>.
<pre> <b>
  $.ajax({
      type: 'GET',
      url: 'search.php?',
      data: message,   
      dataType: 'json'
  })
</b>
</pre>
<b>Explanation:</b>  The above function sends an AJAX (asynchronous HTTP) request to the <code>search.php</code> (proxy).  The request is a <code>GET</code> request and the request data type is a <code>json</code> format from the server.  
</li>

</ol>

