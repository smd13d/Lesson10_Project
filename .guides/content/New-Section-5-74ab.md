<center><h2>Verify Code from Previous Steps</h2></center>

<ol>
<li>the <code>.done()</code> method returns the jQuery HTTP Response object. This function is executed if the AJAX request succeeds. The function accepts the <b>’data’</b> parameter, which is the data returned by the server.
</li>
<li>
<b><pre><code>&ltscript>
$(document).ready(function(){
$(‘:submit’).click(function(){
var message = ‘q=’ + document.getElementsByTagName(“input”)[0].value; <br>
$.ajax({
type: 'GET’,
url: 'search.php?’,
data: message,
dataType: ‘json’
})<br>
.done(function(json){ <br>
var items = json.d.results;
var articleEl = document.getElementsByTagName(“article”)[0];<br>
for (var i = 0; i < items.length; i++) {<br>
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
})//end of done <br>
.fail(function() {
alert(“Posting failed.”);
}); <br>
return false;<br>
});//end of submit<br>
});//end of ready <br>
&lt/script>
</code></pre></b>
</li>

<li>The above code should be placed above the <code>&lt/body> &lt/html></code></li> tags!
</ol>