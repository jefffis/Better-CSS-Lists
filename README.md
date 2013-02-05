Better-CSS-Lists
================

Get more control over your ordered and unordered lists without needing extra images or http requests.

Using **HTML5 Data Attributes & CSS Pseudo Content**, we can render out anything here as the list item marker. HTML character codes work beautifully, so do Unicode characters (if proper headers are sent). This is also great for appending commas or periods to each list item, as you see fit.

Works swimmingly in modern browsers, as well as IE8 and up. Also, this is naturally **resolution independent**, thus it'll look great on any screen.

It's very simple to use; just something like this will work for the markup:


```
<ol>
  <li>Wes anderson cred vegam</li>
</ol>
<ul>
  <li data-item="&hearts;">Wes anderson cred vegam</li>
</ul>
```

And for the CSS:

```
li {
  list-style:none;
  position:relative;
  counter-increment:this; /** name the counter **/
}
li:before {
  content:attr(data-item); /** or whatever you name your data-attribute **/
  position:absolute;
  left:0;
  top:.2em;
  font-size:80%;
  color:white;
  /** this is arbitrary for my design, but you get the idea **/
}
ol li:before {
 content:'(' counter(this) ')'; /** call the counter you named **/
}
```

You'll need to tweak things here and there of course, but you get the concept.