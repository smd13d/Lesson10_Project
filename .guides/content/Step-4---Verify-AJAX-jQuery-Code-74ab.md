<center><h2>Verify Code from Previous Steps</h2></center>

<ol>

The <code>.done()</code> method returns the jQuery HTTP Response object. This function is executed if the AJAX request succeeds. The function accepts the <b>’data’</b> parameter, which is the data returned by the server.
<li>
<b><pre><code>&ltscript><br>$(document).ready(function(){
   $(':submit').click(function(){ 
        var message = 'q=' + document.getElementsByTagName("input")[0].value;  
             $.ajax({
                   type: 'GET',
                   url: 'search.php?',
                   data: message,   
                   dataType: 'json'
              })
                .done(function(json){                   
                      var items = json.d.results;
                      var articleEl = document.getElementsByTagName("article")[0];<br>
                      for (var i = 0; i < items.length; i++) {
                         var newDiv = document.createElement("div");
                         var head = document.createDocumentFragment();
                         var newP1 = document.createElement("p");
                         var newP2 = document.createElement("p");
                         var newP3 = document.createElement("p");
                         var newA = document.createElement("a");<br>
                         head.appendChild(newP1);
                         newA.innerHTML = items[i].Title;
                         newA.setAttribute("href", items[i].Url);<br>
                         newP1.appendChild(newA);
                         newP1.className = "head";
                         newP2.innerHTML = items[i].Url;
                         newP2.className = "url";
                         newP3.innerHTML = items[i].Description;<br>
                         newDiv.appendChild(head);
                         newDiv.appendChild(newP2);
                         newDiv.appendChild(newP3);
                         articleEl.appendChild(newDiv);
                      }//end of for                   
                 })//end of done               
                .fail(function() {
                      alert("Posting failed.");              
                });            
          return false;
      });//end of submit
  });//end of ready      
 &lt/script>  
</code></pre></b>
</li>

<li>The above code should be placed above the <code>&lt/body> &lt/html></code> tags!</li>

</ol>


