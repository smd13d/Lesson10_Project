<center><h2><code>.done()</code> Method to Process HTTP Response from Server</h2></center>

<ol>
<li>the <code>.done()</code> method returns the jQuery HTTP Response object. This function is executed if the AJAX request succeeds. The function accepts the <b>’data’</b> parameter, which is the data returned by the server.
</li>
<li>
After the <code>$.ajax()</code> method add the <code>$.done()</code> method. Insert the following code:

<b><pre><code>.done(function(json){ <br><br>
})//end of done
</code></pre></b>
</li>
<li>The <code>$.done()</code> method retrieves the data from the server and stores it in the <code>json</code> variable. The following steps add the code that will process the data received from the server and add it to the HTML document (the search result).
</li>
<li>Add the following code at the top of the <code>.done()</code> function:
<b><pre><code>var items = json.d.results;<br>var articleEl = document.getElementsByTagName(“article”)[0];</code></pre></b>
<b>Explanation:</b> These lines of code are responsible for storing the <code>d.results</code> which is retrieved from <code>Bing</code> and storing it in the <code>items</code> variable and finding the <code>article</code> tag to store the search result.
</li>
<li>Add the following <code>for loop</code> to create the DOM elements to place the search result on the HTML document. Add the loop below the previous step, inside the <code>.done()</code> function:
<b><pre><code>
for (var i = 0; i < items.length; i) {<br>
var newDiv = document.createElement(“div”);
var head = document.createDocumentFragment();
var newP1 = document.createElement(“p”);
var newP2 = document.createElement(“p”);
var newP3 = document.createElement(“p”);
var newA = document.createElement(“a”);<br>
head.appendChild(newP1);
newA.innerHTML = items[i].Title;
newA.setAttribute("href", items[i].Url);<br>
newP1.appendChild(newA);
newP1.className = "head";
newP2.innerHTML = items[i].Url;<br>
newP2.className = "url";
newP3.innerHTML = items[i].Description;<br>
newDiv.appendChild(head);
newDiv.appendChild(newP2);
newDiv.appendChild(newP3);
articleEl.appendChild(newDiv);<br>
}//end of for
</code></pre></b>
</li>
<li>
Verify that the <code>.done()</code> function matches the following code:
<b><pre><code>
.done(function(json){ <br>
var items = json.d.results;
var articleEl = document.getElementsByTagName(“article”)[0];<br>
for (var i = 0; i < items.length; i) {<br>
var newDiv = document.createElement(“div”);
var head = document.createDocumentFragment();
var newP1 = document.createElement(“p”);
var newP2 = document.createElement(“p”);
var newP3 = document.createElement(“p”);
var newA = document.createElement(“a”);<br>
head.appendChild(newP1);
newA.innerHTML = items[i].Title;
newA.setAttribute("href", items[i].Url);<br>
newP1.appendChild(newA);
newP1.className = "head";
newP2.innerHTML = items[i].Url;<br>
newP2.className = "url";
newP3.innerHTML = items[i].Description;<br>
newDiv.appendChild(head);
newDiv.appendChild(newP2);
newDiv.appendChild(newP3);
articleEl.appendChild(newDiv);<br>
}//end of for<br>
})//end of done
</code></pre></b>
</li>
<li>
Add the <code>.fail()</code> function below the <code>.done()</code> function. The <code>.fail()</code> function is called when the HTTP Request is rejected.
<b><pre><code>.fail(function() {<br>
alert(“Posting failed.”);<br>
}); //end of fail
</code></pre></b>
</li>

</ol>

100%
(1:0)
 
(guides)
Guide Editor Step 2 -
 ×
4. Step 3 -
 
write 
directleft
directright
Settings
rows
