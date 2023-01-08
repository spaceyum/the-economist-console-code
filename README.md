# -The-Economist-console-code
This code will enable you, a free subscription user, to view and read full articles without any subscription. Valid to this day | 1/8/2023

1) Using Google Chrome, richt click and select "Inspect Element"
2) Open up developer tools and navigate your way to "Console" tab
3) Copy and Paste the following code:

___________________________________________________________________________________________________________________________________________________________

fetch(window.location.href) 
  .then(response => response.text()) 
  .then(data => { 
    var found = data.match(/<p data-caps="initial" class="article__body-text article__body-text--dropcap">[\s\S]+?(<p class="article__body-text">[\s\S]+<\/p>)<\/div><\/section>/m); 
    var parts = document.getElementsByClassName('article__body-text'); 
    parts[1].parentNode.removeChild(parts[1]); 
    parts[0].insertAdjacentHTML('afterend', found[1]); 
  }); 
  
___________________________________________________________________________________________________________________________________________________________

The script fetches the same page again using ajax, extracts the full article and puts it where the short (free) article is.
