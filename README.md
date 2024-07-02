---
title: |
  CSS Notes for Professionals
  by web@petercv.com, PDF https://goalkicker.com/CSSBook
author: "bbauska"
date last editted: "7/1/2024 Mon 2+am"
output: 
  markdown:
    with some style
---

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h1>CSS-Notes4Pros</h1>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>CSS Notes For Professionals - intermediate level CSS learning course.  
All on-line.  No money, unless you'd like to donate. I'm game for that.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h1 align="center">Advanced CSS Notes for Professionals</h1>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h6 align="center">(by web@petercs.com, lecturer - PDF @https://goalkicker.com)</h6>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~ readme.md of CSS Advanced - Notes for Professionals ~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ CSS-Notes4Pros.bauska.github.io ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 01/02. javascript/css logos (01) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image001.jpg"
  style="width:20%"
  title="JavaScript coffee cup logo version"
  alt="JavaScript coffee cup logo version." />
<img src="./images/image002.jpg"
  style="width:20%"
  title="CSS logo"
  alt=" logo." />
</p>

<h2 id="about">About</h2>

<p align="center">Please feel free to share this Markdown &amp; website with anyone, latest
version of this book can be downloaded from:<br>
<a href="https://goalkicker.com/CSSBook">https://goalkicker.com/CSSBook</a></p>

<p align="center">This <i>CSS Notes for Professionals</i> book is compiled from 
<a href="https://archive.org/details/documentation-dump.7z">Stack Overflow 
Documentation</a>, the content is written by the beautiful people at Stack Overflow.<br/>
Text content is released under Creative Commons BY-SA, see credits at
the end of this book whom contributed to the various chapters. Images
may be copyright of their respective owners unless otherwise specified.</p>

<p align="center">This is an unofficial free book created for educational purposes and
is not affiliated with official CSS group(s) or company(s) nor Stack
Overflow. All trademarks and registered trademarks are the property of
their respective company owners.</p>

<p align="center">The information presented in this book is not guaranteed to be correct
nor accurate, use at your own risk.</p>

<p align="center">Please send feedback and corrections to <a href="web@petercv.com">web@petercv.com</a></p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Chapter 1: Getting started with CSS</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch1-1">Section 1.1: External Stylesheet</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>An external CSS stylesheet can be applied to any number of HTML
documents by placing a <b>&lt;link&gt;</b> element in each HTML document.</p>

<p>The attribute rel of the <b>&lt;link&gt;</b> tag has to be set to &quot; $\color{red}{stylesheet}$ &quot;,
and the href attribute to the relative or absolute path to the
stylesheet. While using relative URL paths is generally considered
good practice, absolute paths can be used, too. In HTML5 the type
attribute <a href="https://html.spec.whatwg.org/multipage/semantics.html#the-link-element">
can be omitted</a>.</p>

<p>It is recommended that the <b>&lt;link&gt;</b> tag be placed in the HTML file's <b>&lt;head&gt;</b>
tag so that the styles are loaded before the elements they style.
Otherwise, <a href="http://stackoverflow.com/a/1642259/2397327"> 
users will see a flash of unstyled content</a>.</p>

<h4>Example</h4>
<h4>hello-world.html</h4>

<pre><code>&lt;!DOCTYPE html&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;meta charset="utf-8"/&gt;
    &lt;link rel="stylesheet" type="text/css" href="style.css"&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;Hello world!&lt;/h1&gt;
    &lt;p&gt;I ♥ CSS&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre>

<h4>style.css</h4>

<pre><code>h1 {
  color: green;
  text-decoration: underline;
}

p {
  font-size: 25px;
  font-family: 'Trebuchet MS', sans-serif;
}
</code></pre>

<p>Make sure you include the correct path to your CSS file in the href.
If the CSS file is in the same folder as your HTML file then no path
is required (like the example above) but if it's saved in a folder,
then specify it like this;<br>
href="foldername/style.css"</p>

<pre><code>&lt;link rel="stylesheet" type="text/css" href="foldername/style.css"&gt;</code></pre>

<p>External stylesheets are considered the best way to handle your CSS.
There&apos;s a very simple reason for this: when you&apos;re managing a site
of, say, 100 pages, all controlled by a single stylesheet, and you
want to change your link colors from blue to green, it&apos;s a lot easier
to make the change in your CSS file and let the changes &quot;cascade&quot;
throughout all 100 pages than it is to go into 100 separate pages and
make the same change 100 times. Again, if you want to completely
change the look of your website, you only need to update this one
file.</p>

<p>You can load as many CSS files in your HTML page as needed.</p>

<pre><code>&lt;link rel="stylesheet" type="text/css" href="main.css"&gt;
&lt;link rel="stylesheet" type="text/css" href="override.css"&gt;</code></pre>

<p>CSS rules are applied with some basic rules, and order does matter.
For example, if you have a main.css file with some code in it:</p>

<pre><code>p.green { color: #00ff00; }</code></pre>

<p>All your paragraphs with the &apos;green&apos; class will be written in light
green, but you can override this with another .css file just by
including it *after* main.css. You can have override.css with the
following code follow main.css, for example:</p>

<pre><code>p.green { color: #006600; }</code></pre>

<p>Now all your paragraphs with the &apos;green&apos; class will be written in
darker green rather than light green.</p>

<p>Other principles apply, such as the &apos;!important&apos; rule, specificity,
and inheritance.</p>

<p>When someone first visits your website, their browser downloads the
HTML of the current page plus the linked CSS file. Then when they
navigate to another page, their browser only needs to download the
HTML of that page; the CSS file is cached, so it does not need to be
downloaded again. Since browsers cache the external stylesheet, your
pages load faster.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch1-2">Section 1.2: Internal Styles</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>CSS enclosed in <b>&ltstyle&gt;&lt;/style&gt;</b> tags within an HTML document 
function like an external stylesheet, except that it lives in the HTML document it
styles instead of in a separate file, and therefore can only be applied to the 
document in which it lives. Note that this element <i>must</i> be inside the 
<b>&lt;head&gt;</b> element for HTML validation (though it
will work in all current &lt;head&gt; browsers if placed in body).</p>

<pre><code>&lt;head&gt;
  &lt;style&gt;
    h1 {
      color: green;
      text-decoration: underline;
    }
    p {
      font-size: 25px;
      font-family: 'Trebuchet MS', sans-serif;
    }
  &lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;
  &lt;h1&gt;Hello world!&lt;/h1&gt;
  &lt;p&gt;I ♥ CSS&lt;/p&gt;
&lt;/body&gt;
</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch1-3">Section 1.3: CSS &commat;import rule (one of CSS at-rule)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The &commat;import CSS at-rule is used to import style rules from other style 
sheets. These rules must precede all other types of rules, except &commat;charset 
rules; as it is not a nested statement, &commat;import cannot be used inside 
conditional group at-rules <a href="https://developer.mozilla.org/en/docs/Web/CSS/@import">&commat;import</a>.

<h4>How to use &commat;import</h4>

<p>You can use &commat;import rule in the following ways:</p>

A.  <b>With internal style tag</b>

<pre><code>  <style>
    @import url('/css/styles.css');
  </style></code></pre>

B.  <b>With external stylesheet</b>

<p>The following line imports a CSS file named additional-styles.css in
the root directory into the CSS file in which it appears:</p>

<pre><code>@import '/additional-styles.css';</code></pre>

<p>Importing external CSS is also possible. A common use case are font
files.</p>

<pre><code>@import 'https://fonts.googleapis.com/css?family=Lato';</code></pre>

<p>An optional second argument to &commat;import rule is a list of media
queries:</p>

<pre><code>@import '/print-styles.css' print;
@import url('landscape.css') screen and (orientation: landscape);</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch1-4">Section 1.4: Inline Styles</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Use inline styles to apply styling to a specific element. Note that
this is <b><i>not</i></b> optimal. Placing style rules in a <b>&lt;style&gt;</b> tag or
external CSS file is encouraged in order to maintain a distinction
between content and presentation.</p>

<p>Inline styles override any CSS in a <b>&lt;style&gt;</b> tag or external style
sheet. While this can be useful in some circumstances, this fact more
often than not reduces a project&apos;s maintainability.</p>

<p>The styles in the following example apply directly to the elements to
which they are attached.</p>

<pre><code>&lt;h1 style="color: green; text-decoration: underline;"&gt;Hello world!&lt;/h1&gt;
&lt;p style="font-size: 25px; font-family: 'Trebuchet MS';"&gt;I ♥ CSS&lt;/p&gt;</code></pre>

<p>Inline styles are generally the safest way to ensure rendering
compatibility across various email clients, programs and devices, but
can be time-consuming to write and a bit challenging to manage.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="#ch1-5">Section 1.5: Changing CSS with JavaScript</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Pure JavaScript</h4>

<p>It&apos;s possible to add, remove or change CSS property values with JavaScript 
through an element&apos;s style property.</p>

<pre><code>var el = document.getElementById("element");
el.style.opacity = 0.5;
el.style.fontFamily = 'sans-serif';</code></pre>

<p>Note that style properties are named in lower camel case style. In the
example you see that the css property fontfamily becomes fontFamily in
javascript.</p>

<p>As an alternative to working directly on elements, you can create a 
<b>&lt;style&gt;</b> or <b>&lt;link&gt;</b> element in JavaScript and append it 
to the <b>&lt;body&gt;</b> or <b>&lt;head&gt;</b> of the HTML document.</p>

<h4>jQuery</h4>

<p>Modifying CSS properties with jQuery is even simpler.</p>

<pre><code>$('#element').css('margin', '5px');</code></pre>

<p>If you need to change more than one style rule:</p>

<pre><code>$('#element').css({
  margin:"5px",
  padding:"10px",
  color:"black"
});</code></pre>

<p>jQuery includes two ways to change css rules that have hyphens in them
(i.e. font-size). You can put them in quotes or camel-case the style
rule name.</p>

<pre><code>$('.example-class').css({
  "background-color": "blue", 
  fontSize: "10px" 
});</code></pre>

<h4>See also</h4>

<ul>
  <li>JavaScript documentation - Reading and Changing CSS Style.</li>
  <li>jQuery documentation - CSS Manipulation</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch1-6">Section 1.6: Styling Lists with CSS</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>There are three different properties for styling list-items:
list-style-type, list-style-image, and list-style position, which
should be declared in that order. The default values are disc,
outside, and none, respectively. Each property can be declared
separately, or using the list-style shorthand property.</p>

<p><b>list-style-type</b> defines the shape or type of bullet point used for each list-item.</p>
<p>Some of the acceptable values for list-style-type:</p>

<ul>
  <li>disc</li>
  <li>circle</li>
  <li>square</li>
  <li>decimal</li>
  <li>lower-roman</li>
  <li>upper-roman</li>
  <li>none</li>
</ul>

<p>(For an exhaustive list, see the 
<a href="https://www.w3.org/wiki/CSS/Properties/list-style-type">W3C specification wiki</a>).</p>
<p>To use square bullet points for each list-item, for example, you would use 
the following property-value pair:</p>

<pre><code>li {
  list-style-type: square;
}</code></pre>

<p>The <b>list-style-image</b> property determines whether the list-item
icon is set with an image, and accepts a value of none or a URL that
points to an image.</p>

<pre><code>li {
  list-style-image: url (images/bullet.png);
}</code></pre>

<p>The <b>list-style-position</b> property defines where to position the
list-item marker, and it accepts one of two values: &quot;inside&quot; or
&quot;outside&quot;.</p>

<pre><code>li {list-style-position: inside;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch2">Chapter 2: Structure and Formatting of a CSS Rule</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch2-1">Section 2.1: Property Lists</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Some properties can take multiple values, collectively known as a
<b>property list</b>.

<pre><code>/* Two values in this property list */
span {
  text-shadow: yellow 0 0 3px, green 4px 4px 10px;
}

/* Alternate Formatting */
span {
  text-shadow:
    yellow 0 0 3px,
    green 4px 4px 10px;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch2-2">Section 2.2: Multiple Selectors</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>When you group CSS selectors, you apply the same styles to several
different elements without repeating the styles in your style sheet.
Use a comma to separate multiple grouped selectors.</p>

<pre><code>div, p {color: blue }</code></pre>

<p>So the blue color applies to all <b>&lt;div&gt;</b> elements and all <b>&lt;p&gt;</b>
elements.  Without the comma only <b>&lt;p&gt;</b> elements that are a child of 
a <b>&lt;div&gt;</b> would be red.</p>

<p>This also applies to all types of selectors.</p>

<pre><code>p, .blue, #first, div span{ color : blue }</code></pre>

<p>This rule applies to:</p>

<ul>
  <li><b>&lt;p&gt;</b></li>
  <li>elements of the blue class</li>
  <li>element with the ID first</li>
  <li>every <b>&lt;span&gt;</b> inside of a <b>&lt;div&gt;</b>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch2-3">Section 2.3: Rules, Selectors, and Declaration Blocks</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>A CSS <b>rule</b> consists of a <b>selector</b> (e.g. h1) and <b>declaration block</b> ({}).

<pre><code>h1 {}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch3">Chapter 3: Comments</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch3-1">Section 3.1: Single Line</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>/* This is a CSS comment */
div {
  color: red; /* This is a CSS comment */
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch3-2">Section 3.2: Multiple Line</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>/*
  This
  is
  a
  CSS
  comment
*/
div {
  color: red;
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch4">Chapter 4: Selectors</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>CSS selectors identify specific HTML elements as targets for CSS
styles. This topic covers how CSS selectors target HTML elements.
Selectors use a wide range of over 50 selection methods offered by the
CSS language, including elements, classes, IDs, pseudo-elements and
pseudo-classes, and patterns.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch4-1">Section 4.1: Basic selectors</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| Selector     | Description                                         |
|--------------|-----------------------------------------------------|
|  &ast;       | Universal selector (all elements) |
|  div		   | Tag selector (all <b>&lt;div&gt;</b> elements) |
|  .blue       | Class selector (all elements with class blue) |
|  .blue.red   | All elements with class blue and red (a type of Compound selector) |
|  #headline   | ID selector (the element with "id" attribute set to headline) |
|  :pseudo-class | All Elements with pseudo-class |
|  ::pseudo-element | Element that matches pseudo-element |
|  :lang(en)		| Element that matches :lang declaration, for example <b>&lt;span lang="en"&gt;</b> |
|  div > p			| child selector |
  
<blockquote>
  <b>Note:</b> The value of an ID must be unique in a web page. It is a
  violation of the <a href="https://www.w3.org/TR/html/dom.html#the-id-attribute">
  HTML standard</a> to use the value of an ID more than once in the same document tree.
</blockquote>

<p>A complete list of selectors can be found in the 
<a href="https://www.w3.org/TR/css3-selectors/#selectors">CSS Selectors Level
3 specification</a>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-2">Section 4.2: Attribute Selectors</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Overview</h4>

<p>Attribute selectors can be used with various types of operators that
change the selection criteria accordingly. They select an element
using the presence of a given attribute or attribute value.</p>

| Selector(1)     | Matched element            | Selects elements...                |
|----------------:|----------------------------|------------------------------------|
| &lbrack;attr&rbrack;          | &lt;div attr&gt;                 | With attribute attr                |
| &lbrack;attr='val'&rbrack;    | &lt;div attr="val"&gt;           | Where attribute attr has value val |
| &lbrack;attr~='val'&rbrack;   | &lt;div attr="val val2 val3"&gt; | Where val appears in the           |
|                 |                            | whitespace-separated list of attr  |
| &lbrack;attr^='val'&rbrack;   | &lt;div attr="val1 val2"&gt;     | Where attr's value begins with val |
| &lbrack;attr$='val'&rbrack;   | &lt;div attr="sth aval"&gt;      | Where attr's value ends with val   |
| &lbrack;attr&ast;='val'&rbrack;    | &lt;div attr="somevalhere"&gt;   | Where attr contains val anywhere   |
| &lbrack;attr&vert;='val'&rbrack;   | &lt;div attr="val-sth etc"&gt;   | Where attr's value is exactly val, |
|                 |                            | or starts with val and immediately |
|                 |                            | followed by - (U+002D) |
| &lbrack;attr&vert;='val' i&rbrack; | &lt;div attr="val"&gt;           | Where attr has val, |
|                 |                            | ignoring val's letter casing. |

<b>Notes:</b>

1.  The attribute value can be surrounded by either single-quotes or
    double-quotes. No quotes at all may also work, but it&apos;s not valid
    according to the CSS standard, and is discouraged.

2.  There is no single, integrated CSS4 specification, because it is
    split into separate modules. However, there are &quot;level 4&quot; modules.
    <a href="http://caniuse.com/#feat=css-case-insensitive">See browser support</a>.

<h4>Details<br>
&lbrack;<b>attribute</b>&rbrack;</h4>

<p>Selects elements with the given attribute.</p>

<pre><code>div&lbrack;data-color&rbrack; {
  <b>color</b>: red;
}

<b>&lt;div data-color="red"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div data-color="green"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div data-background="red"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/cezale/1/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute="value"</b>&rbrack;</code></pre>

<p>Selects elements with the given attribute and value.</p>

<pre><code>div&lbrack;data-color="red"&rbrack; {
  <b>color</b>: red;
  }

<b>&lt;div data-color="red"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div data-color="green"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div data-background="blue"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/waxoked/1/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute*="value"</b>&rbrack;</code></pre>

<p>Selects elements with the given attribute and value where the given
attribute contains the given value anywhere (as a substring).</p>

<pre><code>&lbrack;class*= "foo"&rbrack; {
  <b>color</b>: red;
}

<b>&lt;div class="foo-123"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="foo123"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="bar123foo"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="barfooo123"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="barfo0"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/dazige/1/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute~="value"</b>&rbrack;</pre></code>

<p>Selects elements with the given attribute and value where the given
value appears in a whitespace-separated list.</p>

<pre><code>&lbrack;class~="color-red"&rbrack; {
  <b>color</b>: red;
}

<b>&lt;div class="color-red foo-bar the-div"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="color-blue" foo-bar the-div"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/posuhim/1/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute^="value"</b>&rbrack;</code></pre>

<p>Selects elements with the given attribute and value where the given
attribute begins with the value.</p>

<pre><code>&lbrack;class^="foo-"&rbrack; {
  <b>color</b>: red;
}

<b>&lt;div class="foobar-file"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="foobar-file"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="foobar-input"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/yowihi/1/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute$="value"</b>&rbrack;</code></pre>

<p>Selects elements with the given attribute and value where the given
attribute ends with the given value.</p>

<pre><code>&lbrack;class$="file"&rbrack; {
  <b>color</b>: red;
}
<b>&lt;div class="foobar-file"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="foobar-file"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div class="foobar-input"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/yowihi/2/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute&vert;="value"</b>&rbrack;</code></pre>

<p>Selects elements with a given attribute and value where the
attribute&apos;s value can be represented as Value, VALUE, vAlUe 
or any other case-sensitive possibility.</p>

<pre><code>&lbrack;lang&vert;="<b>EN</b>" i&rbrack; {
  <b>color</b>: red;
  }
<b>&lt;div lang="EN-us"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div lang="EN-gb"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div lang="PT-pt"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/yowihi/3/edit?html,css,output">Live Demo on JSBin</a>

<pre><code>&lbrack;<b>attribute</b>=<b>"value" i</b>&rbrack;</code></pre>

<p>Selects elements with a given attribute and value where the
attribute&apos;s value can be represented as Value, VALUE, vAlUe or any
other case-insensitive possibility.</p>

<pre><code>&lbrack;lang|=<b>"EN"</b>&rbrack; {
  <b>color</b>: red;
}
<b>&lt;div lang="EN-us"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div lang="EN-gb"&gt;</b>This will be red<b>&lt;/div&gt;</b>
<b>&lt;div lang="PT-pt"&gt;</b>This will NOT be red<b>&lt;/div&gt;</b></code></pre>

<a href="http://jsbin.com/yowihi/4/edit?html,css,output">Live Demo on JSBin</a>

<h4>Specificity of attribute selectors<br>
0-1-0</h4>

<p>Same as class selector and pseudoclass.</p>

<pre><code>*&lbrack;type=checkbox&rbrack; // 0-1-0</code></pre>

<p>Note that this means an attribute selector can be used to select an
element by its ID at a lower level of specificity than if it was
selected with an ID selector: &lbrack;id=<b>"my-ID"</b>&rbrack; targets the same element as <b>#my-ID</b>
but with lower specificity.</p>

<p>See the Syntax Section for more details.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-3">Section 4.3: Combinators</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<b>Overview</b>
<b>Selector Description</b>

| Selector  | Description |
|-----------|-------------------------------------------------------------------------------------|
| div span |  Descendant selector (all <b>&lt;span&gt;</b>s that are descendants of a <b>&lt;div&gt;</b>) |
| div &gt; span | Child selector (all <b>&lt;span&gt;</b>s that are direct child of a <b>&lt;div&gt;</b>) |
| a ~ span | General Sibling selector (all <b>&lt;span&gt;</b>s that are siblings after an <b>&lt;a&gt;</b>) |
| a + span | Adjacent Sibling selector (all <b>&lt;span&gt;</b> that are immediately after an <b>&lt;a&gt;</b>) |

> <b>Note:</b> Sibling selectors target elements that come after them in
> the source document. CSS, by its nature (it cascades), cannot target
> <i>previous</i> or <i>parent</i> elements. However, using the flex order
> property, a <a href="http://stackoverflow.com/a/36118012/3597276">
> previous sibling selector can be simulated on visual media</a>.

<h4>Descendant Combinator: selector selector</h4>

<p>A descendant combinator, represented by at least one space character
(), selects elements that are a descendant of the defined element.
This combinator selects <b>all</b> descendants of the element (from child
elements on down).</p>

<pre><code>div p {
  <b>color</b>: red;
}

<b>&lt;div&gt;</b>
  <b>&lt;p&gt;</b>My text is red<b>&lt;/p&gt;</b>
  <b>&lt;section&gt;</b>
    <b>&lt;p&gt;</b>My text is red<b>&lt;/p&gt;</b>
  <b>&lt;/section&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;p&gt;</b>My text is not red<b>&lt;/p&gt;</b></code></pre>

<a href="http://jsbin.com/xonafuz/2/edit?html,css,output">Live Demo on JSBin</a>

<p>In the above example, the first two <b>&lt;p&gt;</b> elements are selected since they are
both descendants of the <b>&lt;div&gt;</b>.</p>
<h4>Child Combinator: selector &gt; selector</h4>
<p>The child (&gt;) combinator is used to select elements that are
<b>children</b>, or <b>direct descendants</b>, of the specified element.</p>
<pre><code>div &gt; p {
  <b>color</b>: <span style='color: red;'>red</span>;
}

<b>&lt;div&gt;</b>
  <b>&lt;p&gt;</b>My text is <span style='color: red;'>red</span><b>&lt;/p&gt;</b>
  <b>&lt;section&gt;</b>
    <b>&lt;p&gt;</b>My text is not red<b>&lt;/p&gt;</b>
  <b>&lt;/section&gt;</b>
<b>&lt;/div&gt;</b></code></pre>
<a href="http://jsbin.com/xonafuz/3/edit?html,css,output">Live Demo on JSBin</a>
<p>The above CSS selects only the first <b>&lt;p&gt;</b> element, as it is the only paragraph directly descended from a <b>&lt;div&gt;</b>.</p>
<p>The second <b>&lt;p&gt;</b> element is not selected because it is not a direct child of the <b>&lt;div&gt;</b>.</p>
<h4>Adjacent Sibling Combinator: selector &plus; selector</h4>
<p>The adjacent sibling (+) combinator selects a sibling element that immediate follows a specified element.</p>

<pre><code>p &plus; p {
  <b>color: red;</b>
}

<b>&lt;p&gt;</b>My text is not red<b>&lt;/p&gt;</b>
<b>&lt;p&gt;</b>My text is red<b>&lt;/p&gt;</b>
<b>&lt;p&gt;</b>My text is red<b>&lt;/p&gt;</b>
<b>&lt;hr&gt;</b>
<b>&lt;p&gt;</b>My text is not red<b>&lt;/p&gt;</b></code></pre>

<a href="http://jsbin.com/xonafuz/4/edit?html,css,output">Live Demo on JSBin</a>

<p>The above example selects only those <b>&lt;p&gt;</b> elements which are <i>directly preceded</i> by another <b>&lt;p&gt;</b> element.</p>

<h4>General Sibling Combinator: selector &#126; selector</h4>

<p>The general sibling (&#126;) combinator selects <i>all</i> siblings that follow the specified element.</p>

<pre><code>p &#126; p
  <b>color</b>: <span style='color: red;'>red</span>;
}

<b>&lt;p&gt;</b>My text is not red<b>&lt;/p&gt;</b>
<b>&lt;p&gt;</b>My text is <span style='color: red;'>red</span>&lt;/p&gt;
<b>&lt;hr&gt;</b>
<b>&lt;h1&gt;</b>And now a title&lt;/h1&gt;
<b>&lt;p&gt;</b><span style='color: red;'>My text is red</span><b>&lt;/p&gt;</b></code></pre>

<a href="http://jsbin.com/xonafuz/5/edit?html,css,output">Live Demo on JSBin</a>

The above example selects all <b>&lt;p&gt;</b> elements that are <i>preceded</i> by another <b>&lt;p&gt;</b> element,
whether or not they are immediately adjacent.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-4">Section 4.4: Pseudo-classes</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<p><a href="https://www.w3.org/TR/selectors/#pseudo-classes">Pseudo-classes</a> are <b>keywords</b> 
which allow selection based on information that lies outside of the document tree that cannot 
be expressed by other selectors or combinators. This information can be associate to a
certain state (<a href="https://www.w3.org/TR/selectors/#UIstates">state</a> and 
<a href="https://www.w3.org/TR/selectors/#dynamic-pseudos">dynamic</a> pseudo-classes), to locations 
(<a href="https://www.w3.org/TR/selectors/#structural-pseudos">structural and 
<a href="https://www.w3.org/TR/selectors/#target-pseudo">target</a> pseudo-classes), 
to negations of the former (<a href="https://www.w3.org/TR/selectors/#negation">negation</a> 
pseudo-class) or the languages (<a href="https://www.w3.org/TR/selectors/#lang-pseudo">lang</a> 
pseudo-class). Examples include whether or not a link has been followed (:visited), 
the mouse is over an element (:hover), a checkbox is checked (:checked), etc.</p>

<h4>Syntax</h4>

<pre><code>selector:pseudo-class {
  property: <b>VALUE</b>;
}</code></pre>

<b>List of pseudo-classes:</b>

| Name          | Description |
|---------------|---------------------------------------------------------------------------------|
| <a href="https://www.w3.org/TR/css3-selectors/#the-user-action-pseudo-classes-hover-act">:active</a>  | Applies to any element being activated (i.e. clicked) by the user. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:any">:any</a> | Allows you to build sets of related selectors by creating groups that |
|               | included items will match. This is an alternative to repeating an entire selector. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:target">:target</a>  | Selects the current active #news element (clicked on a URL |
|               | containing that anchor name)
| <a href="https://www.w3.org/TR/css3-selectors/#checked">:checked</a>  | Applies to radio, checkbox, or option elements that are checked |
|               | or toggled into an "on" state. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:default">:default</a> | Represents any user interface element that is the default among a group of |
|               | similar elements. |
| <a href="https://www.w3.org/TR/css3-selectors/#enableddisabled">:disabled</a> | Applies to any UI element which is in a disabled state. |
| <a href="https://www.w3.org/TR/selectors/#empty-pseudo">:empty</a>   | Applies to any element which has no children. |
| <a href="https://www.w3.org/TR/css3-selectors/#enableddisabled">:enabled</a>  | Applies to any UI element which is in an enabled state. |
| <a href="http://tympanus.net/codrops/css_reference/first">:first</a> | Used in conjunction with @page rule, this selects the first page in a |
|               | printed document. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child">:first-child</a>  | Represents any element that is the first child element of its parent. |
| <a href="https://www.w3.org/TR/css3-selectors/#first-of-type-pseudo">:first-of-type</a> | Applies when an element is the first of the selected element type |
|              | inside its parent. This may or may not be the first-child. |
| <a href="https://www.w3.org/TR/css3-selectors/#the-user-action-pseudo-classes-hover-act">:focus</a>  | Applies to any element which has the user's focus. This can be given by the |
|              | user's keyboard, mouse events, or other forms of input. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within">:focus-within</a> | Can be used to highlight a whole section when one element inside it is focused. It matches |
|              | any element that the :focus pseudo-class matches or that has a descendant focused. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen">:full-screen</a>  | Applies to any element displayed in full-screen mode. It selects the whole stack |
|              | of elements and not just the top level element. |
| <a href="https://www.w3.org/TR/css3-selectors/#the-user-action-pseudo-classes-hover-act">:hover</a> | Applies to any element being hovered by the user&apos;s pointing device, but |
|              | not activated. |
| <a href="https://www.w3.org/TR/css3-selectors/#indeterminate">:indeterminate</a> | Applies radio or checkbox UI elements which are neither checked nor |
|             | unchecked, but are in an indeterminate state. This can be due to an |
|             | element's attribute or DOM manipulation. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range">:in-range</a>  | The :in-range CSS pseudo-class matches when an element has |
|             | its value attribute inside the specified range limitations for this element. |
|             | It allows the page to give a feedback that the value currently defined |
|             | using the elements is inside the range limits. |
| <a href="http://tympanus.net/codrops/css_reference/invalid/">:invalid</a>  | Applies to &lt;input&gt; elements whose values are invalid according to |
|             | the type specified in the type= attribute. |
| <a href="https://www.w3.org/TR/css3-selectors/#lang-pseudo">:lang</a>  | Applies to any element who&apos;s wrapping &lt;body&gt; element has a properly |
|             | designated lang= attribute. For the pseudo-class to be valid, it must |
|             | contain a <a href="https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes">valid two or three langauge code</a>. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child">:last-child</a>  | Represents any element that is the last child element of its parent. |
| <a href="https://www.w3.org/TR/css3-selectors/#last-of-type-pseudo">:last-of-type</a>  | Applies when an element is the last of the selected element type inside |
|             | its parent. This may or may not be the last-child. |
| <a href="http://tympanus.net/codrops/css_reference/left_pseudo-class/">:left</a> | Used in conjunction with the &commat;page rule, this selects all the left |
|             | pages in a printed document. |
| <a href="https://www.w3.org/TR/css3-selectors/#the-link-pseudo-classes-link-and-visited">:link | Applies to any links which haven&apos;t been visited by the user. |
| <a href="https://www.w3.org/wiki/CSS/Selectors/pseudo-classes/:not">:not() | Applies to all elements which <b>do not</b> match the value passed to |
|                 | :not(p) or :not(.class-name) for example. It must have a value to be |
|                 | valid and it can only contain one selector. However, youi can chain multiple |
|                 | together.
| <a href="https://www.w3.org/TR/css3-selectors/#nth-child-pseudo">:nth-child | Applies when an element is the n-th element of its parent, where n |
|                       | can be an integer, a mathematical expression (e.g n+3) or the keywords |
|                       | odd or even. |
| <a href="https://www.w3.org/TR/css3-selectors/#nth-of-type-pseudo">:nth-of-type | Applies when an eleent is the n-th element of its parent of the |
|                         | same element type, where n can be an integer, a mathematical |
|                         | expression (e.g n+3) or the keywords odd or even. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child">:only-child | The :only-child CSS pseudo-class represents any element |
|                        | which is the only child of a parent.  This is the same as |
|                        | :first-child:last-child or :nth-child(1):nth-last-child(1), |
|                        | but with a lower specificity. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:optional">:optional | The :optional CSS pseudo-class represents any element |
|                      | that does not have the required attribute set on it. This allows |
|                      | forms to easily indicate optional fields and to style them accordingly. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range">:out-of-range | The :out-of-range CSS pseudo-class matches when an element has its |
|                          | value attribute outside the specified range limitations for this element. |
|                          | It allows the page to give a feedback that the value currently defined using the |
|                          | element is outside the range limits. A value can be outside of a range if it is |
|                          | either smaller or larger than maximum and minimum set values. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown">:placeholder-shown | <b>Experimental:</b> Applies to any form element currently displaying placeholder text. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:read-only">:read-only | Applies to any element which is not editable by the user. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write">:read-write | Applies to any element that is editable by a user, such as <b>&lt;input&gt;</b> elements. |
| <a href="http://tympanus.net/codrops/css_reference/right_pseudo-class">:right | Used in conjunction with the @page rule, this selects all the right pages in a |
|                   | printed document. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:root">:root | Matches the root element of a tree representing the document. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:scope">:scope | CSS pseudo-class matches the elements that are a reference |
|                   | point for selectors to match against. |
| <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:target">:target | Selects the current active #news element (clicked on a URL |
|                    | containing that anchor name). |
| <a href="https://www.w3.org/TR/css3-selectors/#the-link-pseudo-classes-link-and-visited">:visited | Applies to any links which have been visited by the user. |

> The :visited pseudo-class can't be used for most styling in a lot of modern browsers anymore because
> it's a security hole. See this <a href="https://hacks.mozilla.org/2010/03/privacy-related-changes-coming-to-css-visited/">link</a> for reference.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown"><b>Experimental.</b>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-5">Section 4.5: Child Pseudo Class</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
&quot;The :nth-child(an+b) CSS pseudo-class matches an element that has
an+b-1 siblings before it in the document tree, for a given positive
<b>or zero value</b> for n&quot; - &lbrack;MDN :nth-child&rbrack;

| <b>pseudo-selector</b>       | <b>1&nbsp;&nbsp;2&nbsp;&nbsp;&nbsp;3&nbsp;&nbsp;&nbsp;4&nbsp;&nbsp;&nbsp;5&nbsp;&nbsp;&nbsp;6&nbsp;&nbsp;&nbsp;7&nbsp;&nbsp;&nbsp;8&nbsp;&nbsp;&nbsp;9&nbsp;&nbsp;&nbsp;10</b> |
|------------------------------|---------------------------------------------------------------------------------|
| :first-child                 |  ✔ |
| :nth-child (3)                | &nbsp;&nbsp;&nbsp;✔ |
| :nth-child (n+3)              | &nbsp;&nbsp;✔&nbsp;  ✔&nbsp;  ✔&nbsp;  ✔&nbsp;  ✔&nbsp;  ✔&nbsp;  ✔&nbsp;  ✔ |
| :nth-child (3n)               |         ✔       ✔       ✔ |
| :nth-child (3n+1)             | ✔         ✔       ✔       ✔ |
| :nth-child (-n+3)             | ✔  ✔  ✔ |
| :nth-child (odd)              | ✔      ✔      ✔     ✔     ✔ |
| :nth-child (even)             |     ✔      ✔      ✔     ✔        ✔ |
| :last-child                   | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;✔ |
| :nth-last-child(3)            | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;✔ |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-6">Section 4.6: Class Name Selectors</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The class name selector select all elements with the targeted class
name. For example, the class name .warning would select the following
<b>&lt;div&gt;</b> element:

<pre><code>&lt;div class="warning"&gt;
  &lt;p&gt;This would be some warning copy.&lt;/p&gt;
&lt;/div&gt;</code></pre>

<p>You can also combine class names to target elements more specifically.
Let&apos;s build on the example above to showcase a more complicated class
selection.</p>

<h4>CSS:</h4>

<pre><code>.important {
  color: orange;
}
.warning {
  color: blue;
}
.warning .important {
  color: red;
}</code></pre>

<h4>HTML:</h4>

<pre><code><b>&lt;div class="warning"&gt;</b>
  <b>&lt;p&gt;</b>This would be some warning copy.<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b>

<b>&lt;div class="important warning"&gt;</b>
  <b>&lt;p class="important"&gt;</b>This is some really important warning copy.<b>&lt;/p&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<p>In this example, all elements with the .warning class will have a blue
text color, elements with the .important class with have an orange
text color, and all elements that have <i>both</i> the .important and
.warning class name will have a red text color.</p>

<p>Notice that within the CSS, the .warning.important declaration did not have any spaces
between the two class names. This means it will only find elements
which contain both class names warning and important in their class
attribute. Those class names could be in any order on the element.</p>

<p>If a space was included between the two classes in the CSS
declaration, it would only select elements that have parent elements
with a .warning class names and child elements with .important class
names.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-7">Section 4.7: Select element using its ID without the high specificity of the ID selector</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This trick helps you select an element using the ID as a value for an
attribute selector to avoid the high specificity of the ID selector.</p>

<h4>HTML:</h4>

<pre><code><b>&lt;div id="element"&gt;</b>. . .<b>&lt;/div&gt;</b></code></pre>

<h4>CSS</h4>

<pre><code>#element { . . . } /* High specificity will override many selectors */
&lbrack;id="element"&rbrack; { . . .} /* Low specificity, can be overridden easily */</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-8">Section 4.8: The :last-of-type selector</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The :last-of-type selects the element that is the last child, of a particular type,
of its parent. In the example below, the css selects the last
paragraph and the last heading h1.</p>

<pre><code>p: last-of-type {
  <b>background: #C5CAE9;</b>
}

h1: last-of-type {
  <b>background: #CDDC39;</b>
}
<b>&lt;div class="container"&gt;</b>
  <b>&lt;p&gt;</b>First paragraph<b>&lt;/p&gt;</b>
  <b>&lt;p&gt;</b>Second paragraph<b>&lt;/p&gt;</b>
  <b>&lt;p&gt;</b>Last paragraph<b>&lt;/p&gt;</b>
  <b>&lt;h1&gt;</b>Heading 1<b>&lt;/h1&gt;</b>
  <b>&lt;h2&gt;</b>First Heading 2<b>&lt;/h2&gt;</b>
  <b>&lt;h2&gt;</b>Last heading 2<b>&lt;/h2&gt;</b>
<b>&lt;/div&gt;</b></code></pre>

<image left justified>

<a href="http://jsfiddle.net/MadalinaTn/YmMZZ/113/">jsFiddle</a>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-9">Section 4.9: CSS3 :in-range selector example</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code><b>&lt;style&gt;</b>
input:in-range {
  border: 1px solid blue;
}
<b>&lt;/style&gt;</b>

<b>&lt;input</b> type="number" min="10" max="20" value="15"&gt;
<b>&lt;p&gt;</b>The border for this value will be blue<b>&lt;/p&gt;</b></code></pre>

<!-- page 18 -->
<p>The :in-range CSS pseudo-class matches when an element has its value attribute
inside the specified range limitations for this element. It allows the
page to give a feedback that the value currently defined using the
element is inside the range limits.&lbrack;<a href=https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range">1</a>&rbrack;.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-10">Section 4.10: A. The :not pseudo-class example & B. :focuswithin CSS pseudo-class</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
A.  The syntax is presented above.

<p>The following selector matches all <b>&lt;input&gt;</b> elements in an HTML document
that are not disabled and don&apos;t have the class .example:</p>

<h4>HTML:</h4>

<pre><code><b>&lt;form&gt;</b>
  Phone: <b>&lt;input</b> type="tel" class="example"&gt;
  E-mail: <b>&lt;input</b> type="email" disabled="disabled"&gt;
  Pasword: <b>&lt;input</b> type="password"&gt;
&lt;/form&gt;</code></pre>

<h4>CSS:</h4>

<pre><code>input:not(&lbrack;disabled&rbrack;):not(.example){
  <b>background-color</b>: #ccc;
}</code></pre>

<p>The :not() pseudo-class will also support comma-separated selectors in
Selectors Level 4:</p>

<h4>CSS:</h4>

<pre><code>input:not(&lbrack;disabled&rbrack;):not(.example){
  <b>background-color</b>: #ccc;
}</code></pre>

<a href="http://jsbin.com/japere/edit?html,css,output">Live Demo on JSBin</a>

See background syntax here.

B.  The :focus-within CSS pseudo-classHTML:

<h4>HTML:</h4>

<pre><code>  <b>&lt;h3&gt;</b>Background is blue if the input is focused.<b>&lt;/p&gt;</b>
  <b>&lt;div&gt;</b>
    <b>&lt;input</b> type="text"&gt;
  <b>&lt;/div&gt;</b></code></pre>

<h4>CSS:</h4>

<pre><code>div {
  <b>height</b>: 80px;
}
input {
  <b>margin</b>: 30px;
}
div:focus-within {
  <b>background-color</b>: #1565C0;
}</code></pre>


<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<image about 7x7>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!-- page 19 -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-11">Section 4.11: Global boolean with checkbox:checked and &#126; (general sibling combinator)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>With the &#126; selector, you can easily implement a global accessible
boolean without using JavaScript.</p>

<h4>Add boolean as a checkbox</h4>

<p>To the very beginning of your document, add as much booleans as you
want with a unique id and the hidden attribute set:</p>

<pre><code>&lt;input type="checkbox" dis="sidebarShown" hidden /&gt;
&lt;input type="checkbox" dis="darkThemeUsed" hidden /&gt;

/* here begins actual content, for example: */
&lt;div id="container"&gt;
  &lt;div id="sider"&gt;
    /* Menu, Search, ... */
  &lt;/div&gt;
 &lt;/div&gt;
 
 &lt;div id="footer"&gt;
   <!-- ... -->
 &lt;/div&gt;</code></pre>

<h4>Change the boolean&apos;s value</h4>
<!-- page 20 -->
<p>You can toggle the boolean by adding a label with the for attribute set:</p>

<pre><code><b>&lt;label</b> for=&quot;sidebarShown&quot;&gt;Show/Hide the sidebar!<b>&lt;/label&gt;</b></code></pre>

<h4>Accessing boolean value with CSS</h4>

The normal selector (like .color-red) specifies the default
properties. They can be overridden by following true / false
selectors:

<pre><code>/* true: */
&lt;checkbox&gt;:checked &bsim; &lbrack;sibling of checkbox & parent of target&rbrack; &lt;target&gt;

/* false: */
&lt;checkbox*gt;:not(:checked) ~ &lbrack;sibling of checkbox & parent of target&rbrack; &lt;target&gt;</code></pre>

Note that &lt;checkbox&gt;, &lbrack;sibling ...&rbrack; and &lt;target&gt; should be replaced by the proper selectors. &lbrack;sibling ...&rbrack;
can be a specific selector, (often if you're lazy) simply * or nothing if the target is already a sibling of the checkbox.

Examples for the above HTML structure would be:

<pre><code>#sidebarShown:checked ~ #container #sidebar {
  margin-left: 300px;
}

#darkThemeUsed:checked ~ #container,
#darkThemeUsed:checked ~ #footer {
  background: #333;
}</code></pre>

<h4>In action</h4>

See <a href="https://jsfiddle.net/yokosbm0/1/">this fiddle</a> for
an implementation of these global booleans.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-12">Section 4.12: ID selectors</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
ID selectors select DOM elements with the targeted ID. To select an
element by a specific ID in CSS, the &num; prefix is used.

For example, the following HTML div element...

<pre><code>&lt;div id="exampleID"&gt;
  &lt;p&gt;Example&lt;/p&gt;
&lt;/div&gt;</code></pre>

<p>...can be selected by #exampleID in CSS as shown below:</p>

<pre><code>#exampleID {
  width: 20px;
}</code></pre>

<b>Note</b>: The HTML specs do not allow multiple elements with the same ID

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-13">Section 4.13: How to style a Range input</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!-- page 21 -->
<h4>HTML</h4>

<pre><code>&lt;input type="range"&gt;&lt;/input&gt;</code></pre>

<h4>CSS</h4>

| <b>Effect</b>  | <b>Pseudo Selector</b>                             |
|----------------|----------------------------------------------------|
| Thumb          | input&lbrack;type=range&rbrack;::-webkit-slider-thumb, input&lbrack;type=range&rbrack;::-moz-range-thumb, |
|                | input&lbrack;type=range&rbrack;::-ms-thumb               |
| Track          | input&lbrack;type=range&rbrack;::-webkit-slider-runnable-track, input&lbrack;type=range&rbrack;::-moz-range-track, |
|                | input&lbrack;type=range&rbrack;::-ms-track |
| OnFocus        | input&lbrack;type=range&rbrack;:focus |
| Lower part of  | input&lbrack;type=range&rbrack;::-moz-range-progress, input&lbrack;type=range&rbrack;::-mx-fill-lower(not possible |
| the track      | in WebKit browsers currently -JS needed) |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch4-14">Section 4.14: The :only-child pseudo-class selector example</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The :only-child CSS pseudo-class represents any element which is the only 
child of its parent.</p>

<h4>HTML:</h4>

<pre><code>&lt;div&gt;
  &lt;p>This paragraph is the only child of the div, it will have the color blue&lt;/p&gt;
&lt;/div&gt;

&lt;div&gt;
  &lt;p&gt;This paragraph is one of the two children of the div&lt;/p&gt;
  &lt;p&gt;This paragraph is one of the two children of its parent&lt;/p&gt;
&lt;/div&gt;
</code></pre>

<h4>CSS:</h4>

<pre><code>p:only-child {
  color: blue;
}</code></pre>

<p>The above example selects the &lt;p&gt; element that is the unique child from its 
parent, in this case a &lt;div&gt;.</p>

<a href="https://jsbin.com/dizosi/edit?html,css">Live Demo on JSBin</a>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch5">Chapter 5: Backgrounds</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!-- page 22 -->
<p>With CSS you can set colors, gradients, and images as the background
of an element.</p>

<p>It is possible to specify various combinations of images, colors, and
gradients, and adjust the size, positioning, and repetition (among
others) of these.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-1">Section 5.1: Background Color</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The background-color property sets the background color of an element
using a color value or through keywords, such as transparent, inherit
or initial.</p>

<ul>
  <li><b>transparent</b>, specifies that the background color should be
    transparent. This is default.</li>
  <li><b>inherit</b>, inherits this property from its parent element.</li>
  <li><b>initial</b>, sets this property to its default value.</li>
</ul>

This can be applied to all elements, and ::first-letter/::first-line pseudo-elements.

Colors in CSS can be specified by different methods.

<h4>Color names</h4>

<h4>CSS</h4>

<pre><code>div {
  background-color: red; /* red */
}</code></pre>

<h4>HTML</h4>

<pre><code>&lt;div&gt;This will have a red background&lt;/div&gt;</code></pre>

<ul>
  <li>The example used above is one of several ways that CSS has to represent
    a single color.</li>
</ul>

<h4>Hex color codes</h4>

Hex code is used to denote RGB components of a color in base-16
hexadecimal notation. &num;ff0000, for example, is bright red, where the
red component of the color is 256 bits (ff) and the corresponding
green and blue portions of the color is 0 (00).

If both values in each of the three RGB pairings (R, G, and B) are the
same, then the color code can be shortened into three characters (the
first digit of each pairing). &num;ff0000 can be shortened to &num;f00, and
&num;ffffff can be shortened to &num;fff.

Hex notation is case-insensitive.

<pre><code>body {
  background-color: #de1205; /* red */
}

.main {
  background-color: #00f; /* blue */
}</code></pre>

<h4>RGB / RGBa</h4>

Another way to declare a color is to use RGB or RGBa.

RGB stands for Red, Green and Blue, and requires of three separate
values between 0 and 255, put between brackets, that correspond with
the decimal color values for respectively red, green and blue.

RGBa allows you to add an additional alpha parameter between 0.0 and
1.0 to define opacity.

<pre><code>header {
  background-color: rgb(0, 0, 0); /* black */
}
footer {
  background-color: rgba(0, 0, 0, 0.5); /* black with 50% opacity */
}</code></pre>

<h4>HSL / HSLa</h4>

Another way to declare a color is to use HSL or HSLa and is similar to
RGB and RGBa.

HSL stands for hue, saturation, and lightness, and is also often
called HLS:

<ul>
  <li>Hue is a degree on the color wheel (from 0 to 360).</li>
  <li>Saturation is a percentage between 0% and 100%.</li>
  <li>Lightness is also a percentage between 0% and 100%.</li>
</ul>

HSLa allows you to add an additional alpha parameter between 0.0 and
1.0 to define opacity.

</code></pre>li a {
<b>background-color</b>: hsl(120, 100&percnt;, 50&percnt;); /* green */
}
#p1 {
<b>background-color</b>: hsla(120, 100&percnt;, 50&percnt;, .3); /* green with 30% opacity */
}</code></pre>

<b>Interaction with background-image</b>

<p>The following statements are all equivalent:</p>

</code></pre>body {
  background: red;
  background-image: url (
partiallytransparentimage.png
);
}
body {
  background-color: red;
  background-image: url (
    partiallytransparentimage.png);
}
body {
  background-image: url(
    partiallytransparentimage.png);
  background-color: red;
}
body {
  background: redurl (
    partiallytransparentimage.png);
}</code></pre>
<!-- page 24 -->
They will all lead to the red color being shown underneath the image,
where the parts of the image are transparent, or the image is not
showing (perhaps as a result of background-repeat).

Note that the following is not equivalent:

</code></pre>body {
<b>background-image</b>: url(partiallytransparentimage.png);
<b>background</b>: red;
}</code></pre>

Here, the value of background overrides your background-image.

For more info on the background property, see Background Shorthand

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-2">Section 5.2: Background Gradients</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

Gradients are new image types, added in CSS3. As an image, gradients
are set with the background-image property, or the background
shorthand.

There are two types of gradient functions, linear and radial. Each
type has a non-repeating variant and a repeating variant:

<ul>
  <li>linear-gradient()</li>
  <li>repeating-linear-gradient()</li>
  <li>radial-gradient()</li>
  <li>repeating-radial-gradient()</li>
</ul>

<h4>linear-gradient()</h4>

<p>A linear-gradient has the following syntax</p>

<b>background</b>: inear-gradient( &lt;direction&gt;?, &lt;color-stop-1&gt;, &lt;color-stop-2&gt;, ...);

| Value             | Meaning |
|:-----------------:|-----------------------------------------------|
| &lt;direction&gt; | Could be an argument like to top, to bottom, to right or to left; or an angle as 0deg, |
|                   | 90deg... . The angle starts from top and rotates clockwise. Can be specified in deg, grad, rad, |
|                   | or turn. If omitted, the gradient flows from top to bottom. |
| &lt;color-stop-list&gt; | List of colors, optionally followed each one by a percentage or length to display it at. For |
|                   | example, yellow 10%, rgba(0,0,0,.5) 40px, #fff 100%... |


Can be specified in
<ul>
  <li><a href="https://www.w3.org/TR/css3-values/#deg">deg</a>,</li>
  <li><a href="https://www.w3.org/TR/css3-values/#grad">grad</a>,</li>
  <li><a href="https://www.w3.org/TR/css3-values/#rad">rad</a>, or</li>
  <li><a href="https://www.w3.org/TR/css3-values/#turn">turn</a>.</li>
</ul>

For example, this creates a linear gradient that starts from the right and transitions from red to blue.

<pre><code>.linear-gradient {
  <b>background</b>: linear-gradient (to left top, red, blue); /* you can also use 270deg */
}</code></pre>

You can create a diagonal gradient by declaring both a horizontal and vertical starting position.

<pre><code>.diagonal-linear-gradient {
  <b>background</b>: linear-gradient (to left top, red, yellow 10&percnt;);
}</code></pre>
<!-- page 25 -->

It is possible to specify any number of color stops in a gradient by
separating them with commas. The following examples will create a
gradient with 8 color stops

<pre><code>.linear-gradient-rainbow {
  <b>background</b>: linear-gradient(to left, red, orange, yellow, green, blue, indigo, violet)
}</code></pre>

<h4>radial-gradient()</h4>

<pre><code><b>.radial-gradient-simple {
  <b>background</b>: radial-gradient(red, blue);
}
.radial-gradient {
  <b>background</b>: radial-gradient(circle farthest-corner at top left, red, blue);
}</code></pre>

| Value    | Meaning   |
|----------|----------------------------------------------------------------------|
| circle   | Shape of gradient. Values are circle or ellipse, default is ellipse. |
| farthest-corner | Keywords describing how big the ending shape must be. Values  |
|                 | are closest-side, farthest-side, closest-corner, farthest-corner |
| top left   | Sets the position of the gradient center, in the same way as |
|            | background-position. |

<h4>Repeating gradients</h4>

Repeating gradient functions take the same arguments as the above
examples, but tile the gradient across the background of the element.

<pre><code>.bullseye {
  <b>background</b>: repeating-radial-gradient(red, red 10&percnt;, white 10&percnt;, white 20&percnt;);
}
.warning {
  <b>background</b>: repeating-linear-gradient(-45deg, yellow, yellow 10&percnt;, black 10&percnt;, black 20&percnt; );
}</code/</pre>

| <b>Value</b>   | <b>Meaning</b>  |
|----------------|-----------------|
| -45deg         | Angle unit. The angle starts from the top and rotates clockwise. Can be specified in deg, grad, rad, or |
|                | turn. |
| to left        | Direction of gradient, default is to bottom. Syntax: to &lbrack;y-axis(top or bottom)&rbrack; &lbrackx-asis(left OR
|                | right)&rbrack; ie to top right.
| yellow 10%     | Color, optionally followed by a percentage or length to display it at. Repeated two or more times. |


Angle unit(https://www.w3.org/TR/css3-values/#angles)
degres (https://www.w3.org/TR/css3-values/#deg),
grad (https://www.w3.org/TR/css3-values/#grad),
rad(https://www.w3.org/TR/css3-values/#rad),
turn(https://www.w3.org/TR/css3-values/#turn).

Note that HEX, RGB, RGBa, HSL, and HSLa color codes may be used instead of color names. Color names were used
for the sake of illustration. Also note that the radial-gradient syntax is much more complex than linear-gradient, 
and a simplified version is shown here. For a full explanation and specs, see the 
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/radial-gradient">MDN Docs</a>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-3">Section 5.3: Background Image</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The background-image property is used to specify a background image to
be applied to all matched elements. By default, this image is tiled to
cover the entire element, excluding margin.</p>

<pre><code..myClass {
  <b>background-image</b>: url (&apos;/path/to/image.jpg&apos;);
}</code></pre>

<p>To use multiple images as background-image, define comma separated url()</p>

<pre><code>.myClass {
  <b>background-image</b>: url 
  (&apos;/path/to/image.jpg&apos;), url (
  &apos;/path/to/image2.jpg&apos;);
}</code></pre>

<p>The images will stack according to their order with the first declared
image on top of the others and so on.</p>

| <b>Value</b>  |   <b>Result</b>    |
|---------------|--------------------|
| url (&apos;/path/to/image.jpg&apos;) | Specify background image&apos;s path(s) or an image resource specified with data URI |
|                                      | schema (apostrophes can be omitted), separate multiples by comma |
| none | No backgound image |
| initial   | Default value |
| inherit | Inherit parent's value |

<h4>More CSS for Background Image</h4>

This following attributes are very useful and almost essential too.

<b>background-size</b>: xpx ypx &vertbar; x% y%; 
<b>background-repeat</b>: no-repeat &vertbar; repeat &vertbar; repeat-x &vertbar; repeat-y; 
<b>background-position</b>: left offset (px/%) right offset (px/%) &vertbar; center center &vertbar; left top &vertbar; right 
bottom;
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-4">Section 5.4: Background Shorthand</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

The background property can be used to set one or more background
related properties:

| <b>Value</b> | <b>Description</b>                                  |
|--------------|--------------------------------------------------|
| back         | Background image to use                          |
| ground-image |                                                  |
|--------------|--------------------------------------------------|
| back         | Background color to apply                        |
| ground-color |                                                  |
|--------------|--------------------------------------------------|
| backgro      | Background image&apos;s position                 |
| und-position |                                                  |
|--------------|--------------------------------------------------|
| bac          | Background image&apos;s size                     |
| kground-size |                                                  |
|--------------|--------------------------------------------------|
| backg        | How to repeat background image                   |
| round-repeat |                                                  |
|--------------|--------------------------------------------------|
| backg        | How the background is positioned (ignored when   |
| round-origin | background-attachment is fixed)                  |
|--------------|--------------------------------------------------|
| bac          | How the background is painted relative to the    |
| kground-clip | content-box, border-box, or the padding-box      |
|--------------|--------------------------------------------------|
| How the      |                                                  |
| background   |                                                  |
| image        |                                                  |
| behaves,     |                                                  |
| whether it   |                                                  |
| scrolls      |                                                  |
| along with   |                                                  |
| its          |                                                  |
| containing   |                                                  |
|              |                                                  |
| backgroun    |                                                  |
| d-attachment |                                                  |
| block or has |                                                  |
| a fixed      |                                                  |
| position     |                                                  |
| within the   |                                                  |
| viewport     |                                                  |
|--------------|--------------------------------------------------|
| initial Sets |                                                  |
| the property |                                                  |
| to value to  |                                                  |
| default      |                                                  |
|--------------|--------------------------------------------------|
| inherit      |                                                  |
| Inherits     |                                                  |
| property     |                                                  |
| value from   |                                                  |
| parent       |                                                  |

> The order of the values does not matter and every value is optional
> <b>Syntax</b>
>
> The syntax of the background shorthand declaration is:
>
> <b>background</b>: &lbrack;&lt;background-image&gt;&rbrack; &lbrack;&lt;background-color&gt;&rbrack;
> &lbrack;&lt;background-position&gt;&rbrack;/&lbrack;&lt;background-size&gt;&rbrack;
>
> &lbrack;&lt;background-repeat&gt;&rbrack; &lbrack;&lt;background-origin&gt;&rbrack;
> &lbrack;&lt;background-clip&gt;&rbrack; &lbrack;&lt;background-attachment&gt;&rbrack;
> &lbrack;&lt;initial&vertbar;inherit&gt;&rbrack;;
>
> <b>Examples</b>

```
<b>background</b>: red;
```

Simply setting a background-color with the redvalue.

```
<b>background</b>: border-box red;
```

Setting a background-clip to border-box and a background-color to red.

```
<b>background</b>: no-repeat center url(&quot;somepng.jpg&quot;);
```

> Sets a background-repeat to no-repeat, background-origin to center and
> a background-image to an image.

```
<b>background</b>: url(&apos;pattern.png&apos;)
  green;
```

> In this example, the background-color of the element would be set to
> green with pattern.png, if it is available, overlayed on the colour,
> repeating as often as necessary to fill the element. If pattern.png
> includes any transparency then the green colour will be visible behind
> it. <b>background</b>: #000000 url(&quot;picture.png&quot;) top left / 600px auto
> no-repeat;
>
> In this example we have a black background with an image
> &apos;picture.png&apos; on top, the image does not repeat in either axis and
> is positioned in the top left corner. The / after the position is to
> be able to include the size of the background image which in this case
> is set as 600px width and auto for the height. This example could work
> well with a feature image that can fade into a solid colour.
>
> <b>NOTE:</b> Use of the shorthand background property resets all
> previously set background property values, even if a value is not
> given. If you wish only to modify a background property value
> previously set, use a longhand property instead.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-5">Section 5.5: Background Size</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> <b>General overview</b>
>
> The
> &lbrack;&lbrack;background-size&rbrack;&rbrack;(https://www.w3.org/TR/2014/CR-css3-background-20140909/#the-background-size)
> property enables one to control the scaling of the background-image.
> It takes up to two values, which determine the scale/size of the
> resulting image in vertical and and horizontal direction. If the
> property is missing, its deemed auto in both width and height.
>
> auto will keep the image&apos;s aspect ratio, if it can be determined. The
> height is optional and can be considered auto. Therefore, on a 256 px
> × 256 px image, all the following background-size settings would yield
> an image with height and width of 50 px:

```
<b>background-size</b>: 50px;
<b>background-size</b>: 50px auto;
/* same as above */
<b>background-size</b>: auto 50px;
<b>background-size</b>: 50px 50px;
```

> So if we started with the following picture (which has the mentioned
> size of 256 px × 256 px),
>
> we&apos;ll end up with a 50 px × 50 px on the user&apos;s screen, contained in
> the background of our element:
>
> One can also use percentage values to scale the image with respect of
> the element. The following example would yield a 200 px × 133 px drawn
> image:

```
#withbackground {
  <b>background-image</b>: url(*to/some/background.png*);
  <b>background-size</b>: 100&percnt; 66&percnt;;
  <b>width</b>:200px;
  <b>height</b>: 200px;
  <b>padding</b>: 0;
  <b>margin</b>: 0; 
}
```

The behaviour depends on the

&lbrack;background-origi&rbrack;

(https://www.w3.org/TR/2014/CR-css3-background-20140909/#the-background-origin)

> <b>Keeping the aspect ratio</b>
>
> The last example in the previos section lost its original aspect
> ratio. The circle got into an ellipse, the square into a rectangle,
> the triangle into another triangle.
>
> The length or percentage approach isn&apos;t flexible enough to keep the
> aspect ratio at all times. auto doesn&apos;t help, since you might not
> know which dimension of your element will be larger. However, to cover
> certain areas with an image (and correct aspect ratio) completely or
> to contain an image with correct aspect ratio completely in a
> background area, the values, contain and cover provide the additional
> functionality.
>
> <b>Eggsplanation for contain and cover</b>
>
> Sorry for the bad pun, but we&apos;re going to use a &lbrack;&lbrack;picture of the day
> by Biswarup
> Ganguly&rbrack;&rbrack;(https://commons.wikimedia.org/wiki/File:Chicken_Egg_without_Eggshell_5859.jpg)
> for demonstration. Lets say that this is your screen, and the gray
> area is outside of your visible screen. For demonstration, We&apos;re
> going to assume a 16 × 9 ratio.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 07.  (xx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image007.png"
  style="width:50%"
  title=""
  alt="." />
</p>
<!-- [image007.png 4.95x2.79](./images/image007.png) -->

> We want to use the aforementioned picture of the day as a background.
> However, we cropped the image to 4x3 for some reason. We could set the
> background-size property to some fixed length, but we will focus on
> contain and cover. Note that I also assume that we didn&apos;t mangle the
> width and/or height of body.

<b>contain</b>

contain

Scale the image, while preserving its intrinsic aspect ratio (if any),
to the largest size such that both its

width and its height can fit inside the background positioning area.

> This makes sure that the background image is always completely
> contained in the background positioning area, however, there could be
> some empty space filled with your background-color in this case:

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 09.  (xx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image009.png"
  style="width:50%"
  title=""
  alt="." />
</p>

<b>cover</b>

cover

Scale the image, while preserving its intrinsic aspect ratio (if any),
to the smallest size such that both its

width and its height can completely cover the background positioning
area.

> This makes sure that the background image is covering everything.
> There will be no visible background-color, however depending on the
> screen&apos;s ratio a great part of your image could be cut off:

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 11.  (xx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image011.png"
  style="width:50%"
  title=""
  alt="." />
</p>
<!-- {width="4.958333333333333in" height="2.7916666666666665in"} -->

<b>Demonstration with actual code</b>

```
div &gt; div {
  <b>background-image</b>: url(http://i.stack.imgur.com/r5CAq.jpg);
  <b>background-repeat</b>: no-repeat;
  <b>background-position</b>: center center;
  <b>background-color</b>: #ccc;
  <b>border</b>: 1px solid;
  <b>width</b>: 20em;
  <b>height</b>: 10em;
}
div .contain {
  <b>background-size</b>: contain;
}
div .cover {
  <b>background-size</b>: cover;
}
```

<i>Additional styles for the explanation boxes</i>

```
div &gt; div {
  <b>margin</b>: 0 1 ex 1 ex 0;
  <b>float</b>: left;
}
div &plus; div {
  <b>clear</b>: both;
  <b>border-top</b>: 1px dashed silver;
  <b>padding-top</b>: 1ex;
}
div &gt; div::after {
  <b>background-color</b>: #000;
  <b>color</b>: #fefefe;
  <b>margin</b>: 1ex;
  <b>padding</b>: 1ex;
  <b>opacity</b>: 0.8;
  <b>display</b>: block;
  <b>width</b>: 10ex;
  <b>font-size</b>: 0.7em;
  <b>content</b>: attr (
    class 
  );
}
  <b>&lt;div&gt;</b>
  <b>&lt;div class = &quot;contain&quot;</b>
  <b>&gt;/div&lt;&gt;</b>
  <b>&lt;p&gt;</b>
```

Note the grey background. The image does not cover the whole region, but
it&apos;s fully

```
<b>&lt;</b>
<b>em</b>
<b>&gt;</b>
contained
<b>&lt;</b>
<b>/em</b>
<b>&gt;</b>
.
<b>/p</b>
<b>&lt;</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
class = &quot;cover&quot;
<b>&gt;</b>
<b>/div</b>
<b>&lt;</b>
<b>&gt;</b>
<b>&lt;</b>
<b>p</b>
<b>&gt;</b>
```

Note the ducks/geese at the bottom of the image. Most of the water is
cut, as well as a part of the sky. You don&apos;t see the complete 
image anymore, but neither do you see any background color;

```
the image
<b>&lt;</b>
<b>em</b>
<b>&gt;</b>
covers
<b>&lt;</b>
<b>/em</b>
<b>&gt;</b>
all of the
<b>&lt;</b>
<b>code</b>
<b>&gt;</b>
&lt;
div
&gt;
<b>&lt;</b>
<b>/code</b>
<b>&gt;</b>
.
<b>&lt;</b>
<b>/p</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-6">Section 5.6: Background Position</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The
> &lbrack;&lbrack;background-position&rbrack;&rbrack;(https://drafts.csswg.org/css-backgrounds-3/#background-position)
> property is used to specify the starting position for a background
> image or gradient

```
.myClass
{
<b>background-image</b>
:
url
(
&apos;path/to/image.jpg&apos;
)
;
<b>background-position</b>
:
50
&percnt;
50
&percnt;
;
}
```

> The position is set using an <b>X</b> and <b>Y</b> co-ordinate and be set
> using any of the units used within CSS.

<b>Unit Description</b>

> A percentage for the horizontal offset is relative to *(width of
> background positioning area - width of background image)*.
>
> *value*% *value*% A percentage for the vertical offset is relative to
> *(height of background positioning area - height of background image)*
>
> The size of the image is the size given by background-size.
>
> Offsets background image by a length given in pixels relative to the
> top left of the background *value*px *value*px positioning area
>
> Units in CSS can be specified by different methods (see here).
>
> <b>Longhand Background Position Properties</b>
>
> In addition to the shorthand property above, one can also use the
> longhand background properties backgroundposition-x and
> background-position-y. These allow you to control the x or y positions
> separately.
>
> <b>NOTE:</b> This is supported in all browsers except Firefox (versions
> 31-48)
> &lbrack;&lbrack;2&rbrack;&rbrack;(http://caniuse.com/#search=background-position-x).
> Firefox 49, to be released September 2016, *will* support these
> properties. Until then, &lbrack;&lbrack;there is a Firefox hack within this
> Stack&rbrack; &lbrack;Overflow
> answer.&rbrack;&rbrack;(http://stackoverflow.com/questions/14844407/background-position-y-doesnt-work-in-firefox-via-css/29282573#29282573)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-7">Section 5.7: The background-origin property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
> The background-origin property specifies where the background image is
> positioned.
>
> Note: If the background-attachment property is set to fixed, this
> property has no effect. Default value: padding-box
>
> Possible values:
>
> padding-box - The position is relative to the padding box border-box -
> The position is relative to the border box content-box - The position
> is relative to the content box initial inherit
>

<h4>CSS</h4>

<pre><code>
.example
{
<b>width</b>: 300px;
<b>border</b>: 20px solid black;
<b>padding</b>: 50px;
<b>background</b>: url (
*https://static.pexels.com/photos/6440/magazines-desk-work-workspace-medium.jpg*
);
<b>background-repeat</b>: no-repeat;
}

.example1 {
}
.example2 {
<b>background-origin</b>: border-box;
}
.example3 {
<b>background-origin</b>: content-box;
}</code></pre>


<h4>HTML</h4>

```
<b>&lt;</b>
<b>p</b>
<b>&gt;</b>
No background-origin (padding-box is default):
<b>&lt;</b>
<b>/p</b>
<b>&gt;</b>
<b>&lt;div</b> class=&quot;example example1&quot;<b>&gt;</b>

<b>&lt;h2&gt;</b>Lorem Ipsum Dolor<b>&lt;/h2&gt;</b> <b>&lt;p&gt;</b>Lorem ipsum dolor sit
amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod
tincidunt ut laoreet dolore magna aliquam erat volutpat.<b>&lt;/p&gt;</b>
<b>&lt;p&gt;</b>Ut wisi enim ad minim veniam, quis nostrud exerci tation
ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo
consequat.<b>&lt;/p&gt; &lt;/div&gt;</b>

**&lt;p&gt;**background-origin: border-box:**&lt;/p&gt;**

**&lt;div** class=&quot;example example2&quot;**&gt;**

**&lt;h2&gt;**Lorem Ipsum Dolor**&lt;/h2&gt;** **&lt;p&gt;**Lorem ipsum dolor sit
amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod
tincidunt ut laoreet dolore magna aliquam erat volutpat.**&lt;/p&gt;**
**&lt;p&gt;**Ut wisi enim ad minim veniam, quis nostrud exerci tation
ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo
consequat.**&lt;/p&gt; &lt;/div&gt;**

**&lt;p&gt;**background-origin: content-box:**&lt;/p&gt;**

**&lt;div** class=&quot;example example3&quot;**&gt;**

**&lt;h2&gt;**Lorem Ipsum Dolor**&lt;/h2&gt;** **&lt;p&gt;**Lorem ipsum dolor sit
amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod
tincidunt ut laoreet dolore magna aliquam erat volutpat.**&lt;/p&gt;**
**&lt;p&gt;**Ut wisi enim ad minim veniam, quis nostrud exerci tation
ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo
consequat.**&lt;/p&gt; &lt;/div&gt;** 
```

Result:

[image013](./images/image013.jpg)

> More:

&lbrack;&lbrack;https://www.w3.org/TR/css3-background/#the-background-origin&rbrack;&rbrack;(https://www.w3.org/TR/css3-background/#the-background-origin)
&lbrack;&lbrack;https://developer.mozilla.org/en-US/docs/Web/CSS/background-origin&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/background-origin)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-8">Section 5.8: Multiple Background Image</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> In CSS3, we can stack multiple background in the same element.

```
#mydiv {
  **background-image**: url(img_1.png), /* top image */
url (img_2.png), /* middle image */
url (img_3.png); /* bottom image */
  **background-position**: right bottom, left top, right top;
  **background-repeat**: no-repeat, repeat, no-repeat;
}
```

Images will be stacked atop one another with the first background on
top and the last background in the back. img_1 will be on top, the
img_2 and img_3 is on bottom.

We can also use background shorthand property for this:

```
#mydiv {
  **background**: 
  url(img_1.png) right bottom no-repeat,
  url(img_2.png) left top repeat,
  url(img_3.png) right top no-repeat;
}
```

We can also stack images and gradients:

```
#mydiv {
  **background**:
url(*image.png*) right bottom no-repeat,
linear-gradient (
  to bottom,
  #fff 0 &percnt;
,
  #000 100 &percnt;
);
}
```

[jsFiddle ](https://jsfiddle.net/z30up2un/)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-9">Section 5.9: Background Attachment</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The background-attachment property sets whether a background image is
> fixed or scrolls with the rest of the page.

```
body {
**background-image**: url(&apos;img.jpg&apos;);
**background-attachment**: fixed;
}
```

**Value Description**
> scroll The background scrolls along with the element. This is default.
> fixed The background is fixed with regard to the viewport. local The
> background scrolls along with the element&apos;s contents. initial Sets
> this property to its default value. inherit Inherits this property
> from its parent element.
>
> **Examples**
***background-attachment: scroll***
> The default behaviour, when the body is scrolled the background
> scrolls with it:

```
body {
**background-image**: url(&apos;image.jpg&apos;);
**background-attachment**: scroll;
}
```

***background-attachment: fixed***
> The background image will be fixed and will not move when the body is
> scrolled:

```
body {
  **background-image**: url(&apos;image.jpg&apos;);
  **background-attachment**: fixed;
}
```

***background-attachment: local***
> The background image of the div will scroll when the contents of the
> div is scrolled.

```
div {
  **background-image**: url(&apos;image.jpg&apos;);
  **background-attachment**: local;
}
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-10">Section 5.10: Background Clip</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Definition and Usage: The background-clip property specifies the
> painting area of the background.
>
> Default value: border-box
>
> Values
>
> border-box is the default value. This allows the background to extend
> all the way to the outside edge of the element&apos;s border. padding-box
> clips the background at the outside edge of the element&apos;s padding and
> does not let it extend into the border; content-box clips the
> background at the edge of the content box.
>
> inherit applies the setting of the parent to the selected element.
>

<h4>CSS</h4>

```
.example {
  **width**:300px;
  **border**:20px solid black;
  **padding**:50px;
  **background**:url (
    https://static.pexels.com/photos/6440/magazines-desk-work-workspace-medium.jpg
  );
  **background-repeat**: no-repeat;
}
.example1 {
}
.example2 {
  **background-origin**: border-box;
}
.example3 {
  **background-origin**: content-box;
}
```

<h4>HTML</h4>

```
**&lt;**
**p**
**&gt;**
No background-origin (padding-box is default):
**&lt;**
**/p**
**&gt;**
**&lt;**
**div**
class
=
&quot;example example1&quot;
**&gt;**
**&lt;**
**h**
**2**
**&gt;**
Lorem Ipsum Dolor
**&lt;**
**/h**
**2**
<b>&gt;</b>
<b>&lt;</b>
<b>p</b>
<b>&gt;</b>
Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
nonummy nibh euismod
tincidunt ut laoreet dolore magna aliquam erat volutpat.
<b>&lt;</b>
<b>/p</b>
<b>&gt;</b>
<b>&lt;</b>
<b>p</b>
<b>&gt;</b>
Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper
suscipit lobortis nisl ut
aliquip ex ea commodo consequat.
<b>&lt;</b>
<b>/p</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>p</b>
<b>&gt;</b>
background-origin: border-box:
<b>&lt;</b>
<b>/p</b>
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
class = &quot;example example2&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>h</b>
<b>2</b>
<b>&gt;</b>
Lorem Ipsum Dolor
<b>&lt;</b>
<b>/h</b>
<b>2</b>
<b>&gt;</b>
<b>&lt;</b>
<b>p</b>
<b>&gt;</b>
Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam
nonummy nibh euismod
tincidunt ut laoreet dolore magna aliquam erat volutpat.
<b>&lt;</b>
<b>/p</b>
<b>&gt;</b>
<b>&lt;</b>
<b>p</b>
<b>&gt;</b>
Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper
suscipit lobortis nisl ut
aliquip ex ea commodo consequat.
<b>&lt;</b>
<b>/p</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>p</b>
<b>&gt;</b>
background-origin: content-box:
<b>&lt;</b>
<b>/p</b>
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
class
=
&quot;example example3&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>h</b>
<b>2</b>
<b>&gt;</b>
Lorem Ipsum Dolor
<b>&lt;</b>
<b>/h</b>
<b>2</b>
<b>&gt;</b>
> <b>&lt;p&gt;</b>There once was a man fron Sash. His balls were made of glass
> When he rubbed them together, he made stormy weather.
> And lightning struck out of his ass.<b>&lt;/p&gt;</b> <b>&lt;p&gt;</b>And more goes here, as
> well. It beats Latin. I don't know Latin so better for me
> the end.<b>&lt;/p&gt; &lt;/div&gt;</b>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-11">Section 5.11: Background Repeat</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

The background-repeat property sets if/how a background image will be repeated.

By default, a background-image is repeated both vertically and horizontally.

```
div {
  <b>background-image</b>: url (
    &quot;img.jpg&quot;
  );
  <b>background-repeat</b>: repeat-y;
}
  <b>background-repeat</b>: repeat-y
```

<h4>Here&apos;s how it looks:</h4>

[image014.jpg](./images/image014.jpg)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-12">Section 5.12: background-blend-mode Property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
.my-div
{
<b>width</b>:300px;
<b>height</b>:200px;
<b>background-size</b>:100&percnt;;
<b>background-repeat</b>:no-repeat;
<b>background-image</b>:linear-gradient
(
to right, black 0&percnt;
,white 100&percnt;
),
url
(
&apos;https://static.pexels.com/photos/54624/strawberry-fruit-red-sweet-54624-medium.jpeg&apos;
);
<b>background-blend-mode</b>:saturation;
}
<b>&lt;</b>
<b>div</b>
class
=
&quot;my-div&quot;
<b>&gt;</b>
Lorem ipsum
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
```

<a href="https://jsfiddle.net/MadalinaTn/y69d28Lb/&rbrack;&rbrack;(https://jsfiddle.net/MadalinaTn/y69d28Lb/">See results here</a>.

> CSS Syntax: background-blend-mode: normal &vertbar; multiply &vertbar; screen &vertbar;
> overlay &vertbar; darken &vertbar; lighten &vertbar; color-dodge &vertbar; saturation &vertbar; color &vertbar;
> luminosity;

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch5-13">Section 5.13: Background Color with Opacity</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> If you set opacity on an element it will affect all its child
> elements. To set an opacity just on the background of an element you
> will have to use RGBA colors. Following example will have a black
> background with 0.6 opacity.

/* Fallback for web browsers that don&apos;t support RGBa */

```
<b>background-color</b>:rgb (
  0,0,0
  );
/* RGBa with 0.6 opacity */
<b>background-color</b>:rgba (
  0,0,0,0.6
);
/* For IE 5.5 - 7 */
<b>filter</b>: progid: DXImageTransform.Microsoft.gradient
(
startColorstr = #99000000,
endColorstr = #99000000 
);
/* For IE 8 */
&minus;
ms-filter:
&quot;progid:DXImageTransform.Microsoft.gradient(startColorstr=#99000000,
endColorstr=#99000000)&quot;;
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch6">Chapter 6: Centering</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-1">Section 6.1: Using Flexbox</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML:</h4>

```
<b>&lt;</b>
<b>div</b>
class
=
&quot;container&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>img</b>
src
=
&quot;http://lorempixel.com/400/200&quot;
<b>/&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
```

<h4>CSS:</h4>

```
html, body, .container
{
<b>height</b>:100&percnt;;
}
.container {
<b>display</b>: flex;
<b>justify-content</b>: center;
/* horizontal center */
}
img {
<b>align-self</b>:center;
/* vertical center */
}
```

&lbrack;&lbrack;View Result&rbrack;&rbrack;(https://jsfiddle.net/aLu05kjy/1/) 

<h4>HTML:</h4>

```
<b>&lt;</b>
<b>img</b>
src = &quot;http://lorempixel.com/400/200&quot;
<b>/&gt;</b>
> <b>CSS:</b>
html, body {
<b>height</b>:100&percnt;;
}
body {
<b>display</b>:flex;
<b>justify-content</b>:center;
*/&ast; horizontal center &ast;/*
<b>align-items</b>:center;
/* vertical center */
}
```

&lbrack;&lbrack;View Result&rbrack;&rbrack;(https://jsfiddle.net/ttp0bzfm/1/)

> See Dynamic Vertical and Horizontal Centering under the Flexbox
> documentation for more details on flexbox and what the styles mean.
>
> <b>Browser Support</b>
>
> Flexbox is supported by all major browsers, &lbrack;&lbrack;except IE versions
> before 10&rbrack;&rbrack;(http://caniuse.com/#search=flex).
>
> Some recent browser versions, such as Safari 8 and IE10, require
> &lbrack;&lbrack;vendor
> prefixes&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Glossary/Vendor_Prefix).
>
> For a quick way to generate prefixes there is
> &lbrack;&lbrack;Autoprefixer&rbrack;&rbrack;(https://autoprefixer.github.io/), a
> third-party tool.
>
> For older browsers (like IE 8 & 9) a &lbrack;&lbrack;Polyfill is
> available&rbrack;&rbrack;(https://github.com/jonathantneal/flexibility).
>
> For a more detailed look at flexbox browser support, see &lbrack;&lbrack;this
> answer&rbrack;&rbrack;(http://stackoverflow.com/a/35137869/3597276).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-2">Section 6.2: Using CSS transform</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> CSS transforms are based on the size of the elements so if you don&apos;t
> know how tall or wide your element is, you can position it absolutely
> 50% from the top and left of a relative container and translate it by
> 50% left and upwards to center it vertically and horizontally.
>
> Keep in mind that with this technique, the element could end being
> rendered at a non-integer pixel boundary, making it look blurry. See
> &lbrack;&lbrack;this answer in
> SO&rbrack;&rbrack;(http://stackoverflow.com/a/32329785/1385678) for a
> workaround.

<h4>HTML</h4>

```
<b>&lt;</b>
<b>div</b>
class
=
&quot;container&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
class
=
&quot;element&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
```

<h4>CSS</h4>

```
.container
{
<b>position</b>
:
relative
;
}
.element
{
<b>position</b>
:
absolute
;
<b>top</b>
:
50
&percnt;
;
<b>left</b>
:
50
&percnt;
;
<b>transform</b>
:
translate
(
-50
&percnt;
,
-50
&percnt;
)
;
}
```

&lbrack;&lbrack;View example in
JSFiddle&rbrack;&rbrack;(https://jsfiddle.net/webtiki/rz3p3ufs/)

> <b>CROSS BROWSER COMPATIBILITY</b>
>
> The transform property needs prefixes to be supported by older
> browsers. Prefixes are needed for Chrome&lt;=35, Safari&lt;=8, Opera&lt;=22,
> Android Browser&lt;=4.4.4, and IE9. CSS transforms are not supported by
> IE8 and older versions.
>
> Here is a common transform declaration for the previous example:
>
> -webkit-transform: translate(-50%, -50%); */&ast; Chrome, Safari, Opera,
> Android &ast;/*
>
> -ms-transform: translate(-50%, -50%); */&ast; IE 9 &ast;/* <b>transform</b>:
> translate(-50%, -50%);
>
> For more information see
> &lbrack;&lbrack;canIuse&rbrack;&rbrack;(http://caniuse.com/#feat=transforms2d).
>
> <b>MORE INFORMATION</b>

  <b>position</b>                    :   relative

> The element is being positioned according to the first non-static
> parent ( , absolute, or fixed). Explore more in this
> &lbrack;&lbrack;fiddle&rbrack;&rbrack;(https://jsfiddle.net/siavasfiroozbakht/ox8kyypa/)
> and this documentation topic.

  <b>left</b>   :   50%     and     <b>transform</b>    :   translateX          (   -50%

  </b>top</b>   :   50%     and     <b>transform</b>    :   translateY           (   -50%

> For horizontal-only centering, use ). The same goes for verticalonly
> centering: center with ).

  <b>right</b>   :   -50%       ; and      <b>margin-bottom</b>          :   -50%


> Using a non-static width/height elements with this method of centering
> can cause the centered element to appear squished. This mostly happens
> with elements containing text, and can be fixed by adding:
> <b>margin</b>;. View this
> &lbrack;&lbrack;fiddle&rbrack;&rbrack;(https://jsfiddle.net/4xxmxca0/) for more
> information.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-3">Section 6.3: Using margin: 0 auto;</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

| <b>margin</b>: 0                         | > auto;                      |

> Objects can be centered by using if they are block elements and have a
> defined width.
>
<h4>HTML</h4>

```
<b>&lt;</b>
<b>div</b>
class
=
&quot;containerDiv&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
id
=
&quot;centeredDiv&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
class
=
&quot;containerDiv&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>p</b>
id
=
&quot;centeredParagraph&quot;
<b>&gt;</b>
This is a centered paragraph.
<b>&lt;</b>
<b>/p</b>
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
<b>&lt;</b>
<b>div</b>
class
=
&quot;containerDiv&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>img</b>
id
=
&quot;centeredImage&quot;
src
=
&quot;https://i.kinja-img.com/gawker-media/image/upload/s&minus;-c7Q9b4Eh&minus;-/c_scale,fl_progressive,q_80,w&lowbar;
800
/qqyvc3bkpyl3mfhr8all.jpg&quot;
<b>/&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
```

<h4>CSS</h4>

```
.containerDiv {
  <b>width</b>: 100&percnt;;
  <b>height</b>: 100px;
  <b>padding-bottom</b>: 40px;
}
#centeredDiv {
  <b>margin</b>: 0 auto;
  <b>width</b>: 200px;
  <b>height</b>: 100px;
  <b>border</b>: 1px solid #000;
}
#centeredParagraph {
  <b>width</b>: 200px;
  <b>margin</b>: 0 auto;
}
#centeredImage {
  <b>display</b>: block;
  <b>width</b>: 200px;
  <b>margin</b>: 0 auto;
}
```

> Result:
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 15.  (xx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image015.jpg"
  style="width:50%"
  title=""
  alt="." />
</p>
<!-- [image015.jpg](./images/image015.jpg) -->

JSFiddle example: &lbrack;&lbrack;Centering objects with margin: 0
auto <a href="https://jsfiddle.net/xf1ze3v9/">Demo</a>.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-4">Section 6.4: Using text-align</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

  <b>text-align</b>

> The most common and easiest type of centering is that of lines of text
> in an element. CSS has the rule :
>
> center for this purpose:
>

<h4>HTML</h4>

```
<b>&lt;</b>
<b>p</b>
<b>&gt;</b>
Lorem ipsum
<b>&lt;</b>
<b>/p</b>
<b>&gt;</b>
```

<h4>CSS</h4>

```
p {
  <b>text-align</b>: center;
}
```

> *This does not work for centering entire block elements*. text-align
> controls only alignment of inline content like text in its parent
> block element.
>
> See more about text-align in Typography section.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-5">Section 6.5: Using position: absolute</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> *Working in old browsers (IE &gt;= 8)*
>
> Automatic margins, paired with values of zero for the left and right
> or top and bottom offsets, will center an absolutely positioned
> elements within its parent.

&lbrack;&lbrack;View Result&rbrack;&rbrack;(https://jsfiddle.net/stuttufu/sj2m0oo2/1/)

<h4>HTML</h4>

```
<b>&lt;</b> <b>div</b> class=&quot;parent&quot;<b>&gt;</b>
<b>&lt;</b> <b>img</b> class=&quot;center&quot; src=&quot;http://lorempixel.com/400/200/&quot;<b>/&gt;</b>
<b>&lt;</b> <b>/div</b>
<b>&gt;</b>
```

<h4>CSS</h4>

```
.parent {
  <b>position</b>: relative;
  <b>height</b>: 500px;
}
.center
{
  <b>position</b>: absolute;
  <b>margin</b>: auto;
  <b>top</b>: 0;
  <b>right</b>: 0;
  <b>bottom</b>: 0;
  <b>left</b>: 0;
}
```

Elements that don&apos;t have their own implicit width and height like
images do, will need those values defined.

Other resources: &lbrack;&lbrack;Absolute Centering in
CSS&rbrack;&rbrack;(http://codepen.io/shshaw/details/gEiDt)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-6">Section 6.6: Using calc()</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

  calc              (    100% - 80px

The calc() function is the part of a new syntax in CSS3 in which you
can calculate (mathematically) what size/position your element
occupies by using a variety of values like pixels, percentages, etc.
Note: Whenever you use this function, always take care of the space
between two values ). 

<h4>CSS</h4>

```
.center {
  <b>position</b>: absolute;
  <b>height</b>: 50px;
  <b>width</b>: 50px;
  <b>background</b>: red;
  <b>top</b>: calc (50&percnt; &minus; 50px/2
);
/* height divided by 2 */
  <b>left</b>: calc (50&percnt; &minus; 50px / 2);
/* width divided by 2 */
}
```


<h4>HTML</h4>

```
<b>&lt;</b>
<b>div</b>
class
=
&quot;center&quot;
<b>&gt;</b>
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-7">Section 6.7: Using line-height</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

You can also use line-height to center vertically a single line of
text inside a container :

<h4>CSS</h4>

```
div {
  <b>height</b>: 200px;
  <b>line-height</b>: 200px;
}
  <b>&lt;input</b> <b>/&gt;</b>
```

That&apos;s quite ugly, but can be useful inside an element. The
line-height property works only when the text to be centered spans a
single line. If the text wraps into multiple lines, the resulting
output won&apos;t be centered.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-8">Section 6.8: Vertical align anything with 3 lines of code</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

Supported by IE11+ (http://caniuse.com/#search=transform)

View Result (https://jsfiddle.net/bnqrLgk9/1/)

Use these 3 lines to vertical align practically everything. Just make
sure the div/image you apply the code to has a parent with a height.

<h4>CSS</h4>

```
div
.vertical
{
<b>position</b>
:
relative
;
<b>top</b>
:
50
&percnt;
;
<b>transform</b>
:
translateY
(
-50
&percnt;
)
;
}
```

<h4>HTML</h4>

```
<b>&lt;</b>
<b>div</b>
class
=
&quot;vertical&quot;
<b>&gt;</b>
Vertical aligned text!
<b>&lt;</b>
<b>/div</b>
<b>&gt;</b>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-9">Section 6.9: Centering in relation to another item</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> We will see how to center content based on the height of a near
> element.
>
> Compatibility: IE8+, all other modern browsers.
>
> <h4>HTML</h4>

<b>&lt;</b>

<b>div</b>

class

=

&quot;content&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;position-container&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;thumb&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>img</b>

src

=

&quot;http://lorempixel.com/400/200/&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;details&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>p</b>

class

=

&quot;banner-title&quot;

<b>&gt;</b>

text 1

<b>&lt;</b>

<b>/p</b>

<b>&gt;</b>

<b>&lt;</b>

<b>p</b>

class

=

&quot;banner-text&quot;

<b>&gt;</b>

content content content content content content content content

content content content content content content

<b>&lt;</b>

<b>/p</b>

<b>&gt;</b>

<b>&lt;</b>

<b>button</b>

class

=

&quot;btn&quot;

<b>&gt;<b>

button

<b>&lt;</b>

<b>/button</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

> <h4>CSS</h4>

.content

&ast;

{

<b>box-sizing</b>

:

border-box

;

}

.content

.position-container

{

<b>display</b>

:

table

;

}

.content

.details

{

<b>display</b>

:

table-cell

;

<b>vertical-align</b>

:

middle

;

<b>width</b>

:

33.333333

&percnt;

;

<b>padding</b>

:

30

px

;

<b>font-size</b>

:

17

px

;

<b>text-align</b>

:

center

;

}

.content

.thumb

{

<b>width</b>

:

100

&percnt;

;

}

.content

.thumb

img

{

<b>width</b>

:

100

&percnt;

;

}

> Link to
> &lbrack;&lbrack;JSFiddle&rbrack;&rbrack;(https://jsfiddle.net/gasp10/6bv92mko/4/)
>
> The main points are the 3 .thumb, .details and .position-container
> containers:

  <b>display</b>                         :     table


  <b>width</b>   :   &period;...   and    <b>display</b>   :   table-cell      ,   <b>vertical-align</b>


> The .position-container must have .
>
> The .details must have the real width set : middle.

  <b>width</b>                        :      100%

> The .thumb must have if you want that it will take all the remaining
> space and it will be influenced by the .details width.

  <b>width</b>                        :      100%

> The image (if you have an image) inside .thumb should have , but it is
> not necessary if you have correct proportions.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-10">Section 6.10: Ghost element technique (Michał Czernow&apos;s hack)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> This technique works even when the container&apos;s dimensions are
> unknown.

  <b>vertical-align</b>

> Set up a &quot;ghost&quot; element inside the container to be centered that is
> 100% height, then use :
>
> middle on both that and the element to be centered.
>
> <h4>CSS</h4>

*/&ast; This parent can be any width and height &ast;/*

.block

{

<b>text-align</b>

:

center

;

*/&ast; May want to do this if there is risk the container may be narrower
than the element inside &ast;/*

<b>white-space</b>

:

nowrap

;

}

*/&ast; The ghost element &ast;/*

.block

:

before

{

<b>content</b>

:

&apos;&apos;

;

<b>display</b>

:

inline-block

;

<b>height</b>

:

100

&percnt;

;

<b>vertical-align</b>

:

middle

;

*/&ast; There is a gap between ghost element and .centered,*

*caused by space character rendered. Could be eliminated by*

*nudging .centered (nudge distance depends on font family),*

*or by zeroing font-size in .parent and resetting it back*

*(probably to 1rem) in .centered. &ast;/*

<b>margin-right</b>

:

-0.25

em

;

}

*/&ast; The element to be centered, can also be of any width and height
&ast;/*

.centered

{

<b>display</b>

:

inline-block

;

<b>vertical-align</b>

:

middle

;

<b>width</b>

:

300

px

;

<b>white-space</b>

:

normal

;

*/&ast; Resetting inherited nowrap behavior &ast;/*

}

> <h4>HTML</h4>

<b>&lt;</b>

<b>div</b>

class

=

&quot;block&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>div</b>

class

=

&quot;centered&quot;

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<b>&lt;</b>

<b>/div</b>

<b>&gt;</b>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="6-11">Section 6.11: Centering vertically and horizontally without worrying about height or width</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The following technique allows you to add your content to an HTML
> element and center it both horizontally and vertically **without
> worrying about its height or width**.

  **display**: table;

> **The outer container** should have
>
> **The inner container**

  **display**: table-cell;

  **vertical-align**: middle;

  **text-align**: center;

> should have should have should have
>
> **The content box**

  **display**: inline-block;

  **text-align**: left;           or    **text-align**: right;

> should have
>
> should re-adjust the horizontal text-alignment to eg. , unless you
> want text to be centered
>
> **Demo**
>
> <h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;outer-container&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;inner-container&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;centered-content&quot;

**&gt;**

You can put anything here!

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

body

{

**margin**

:

0

;

}

.outer-container

{

**position**

:

absolute

;

**display**

:

table

;

**width**

:

100

&percnt;

;

*/&ast; This could be ANY width &ast;/*

**height**

:

100

&percnt;

;

*/&ast; This could be ANY height &ast;/*

**background**

:

#ccc

;

}

.inner-container

{

**display**

:

table-cell

;

**vertical-align**

:

middle

;

**text-align**

:

center

;

}

.centered-content

{

**display**

:

inline-block

;

**text-align**

:

left

;

**background**

:

#fff

;

**padding**

:

20

px

;

**border**

:

1

px

solid

#000

;

}

See also &lbrack;**&lbrack;this
Fiddle&rbrack;**&rbrack;(http://jsfiddle.net/WXLsY/621/)!

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-12">Section 6.12: Vertically align an image inside div</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;wrap&quot;

**&gt;**

**&lt;**

**img**

src

=

&quot;http://lorempixel.com/400/200/&quot;

**/&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.wrap

{

**height**

:

50

px

;

*/&ast; max image height &ast;/*

**width**

:

100

px

;

**border**

:

1

px

solid

blue

;

**text-align**

:

center

;

}

.wrap

:

before

{

**content**

:

&quot;&quot;

;

**display**

:

inline-block

;

**height**

:

100

&percnt;

;

**vertical-align**

:

middle

;

**width**

:

1

px

;

}

img

{

**vertical-align**

:

middle

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-13">Section 6.13: Centering with fixed size</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> If the size of your content is fixed, you can use absolute positioning
> to 50% with margin that reduces half of your content&apos;s width and
> height:
>
> <h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;center&quot;

**&gt;**

Center vertically and horizontally

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.center

{

**position**

:

absolute

;

**background**

:

#ccc

;

**left**

:

50

&percnt;

;

**width**

:

150

px

;

**margin-left**

:

-75

px

;

*/&ast; width &ast; -0.5 &ast;/*

**top**

:

50

&percnt;

;

**height**

:

200

px

;

**margin-top**

:

-100

px

;

*/&ast; height &ast; -0.5 &ast;/*

}

> **Horizontal centering with only fixed width**
>
> You can center the element horizontally even if you don&apos;t know the
> height of the content:
>
> <h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;center&quot;

**&gt;**

Center only horizontally

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.center

{

**position**

:

absolute

;

**background**

:

#ccc

;

**left**

:

50

&percnt;

;

**width**

:

150

px

;

**margin-left**

:

-75

px

;

*/&ast; width &ast; -0.5 &ast;/*

}

> **Vertical centering with fixed height**
>
> You can center the element vertically if you know the element&apos;s
> height:
>
> <h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;center&quot;

**&gt;**

Center only vertically

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.center

{

**position**

:

absolute

;

**background**

:

#ccc

;

**top**

:

50

&percnt;

;

**height**

:

200

px

;

**margin-top**

:

-100

px

;

*/&ast; width &ast; -0.5 &ast;/*

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-14">Section 6.14: Vertically align dynamic height elements</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Applying css intuitively doesn&apos;t produce the desired results because

  **vertical-align**:middle

  **margin-top**:auto          and      **margin-bottom**:auto

  **margin-top**:-50%


> &lbrack;***&lbrack;isn&apos;t&rbrack;*** &lbrack;applicable to block-level
> elements&rbrack;&rbrack;(http://www.w3.org/TR/CSS21/visudet.html#propdef-vertical-align)
> &lbrack;&lbrack;used values would compute as&rbrack;
> ***&lbrack;zero&rbrack;***&rbrack;(http://www.w3.org/TR/CSS2/visudet.html#Computing_heights_and_margins)
>
> &lbrack;&lbrack;percentage-based margin values are calculated relative to
> the&rbrack; ***&lbrack;width&rbrack;*** &lbrack;of containing
> block&rbrack;&rbrack;(http://www.w3.org/TR/CSS2/box.html#margin-properties)
>
> For widest browser support, a workaround with helper elements:
>
> <h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;vcenter&minus;-container&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;vcenter&minus;-helper&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;vcenter&minus;-content&quot;

**&gt;**

*&lt;!&minus;-*

*stuff*

*&minus;-&gt;*

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.vcenter

&minus;-

container

{

**display**

:

table

;

**height**

:

100

&percnt;

;

**position**

:

absolute

;

**overflow**

:

hidden

;

**width**

:

100

&percnt;

;

}

.vcenter

&minus;-

helper

{

**display**

:

table-cell

;

**vertical-align**

:

middle

;

}

.vcenter

&minus;-

content

{

**margin**

:

0

auto

;

**width**

:

200

px

;

}

&lbrack;&lbrack;jsfiddle&rbrack;&rbrack;(http://jsfiddle.net/ovfiddle/yVAW9/) from
&lbrack;&lbrack;original
question&rbrack;&rbrack;(http://stackoverflow.com/a/12417336/1081234).
This approach

> works with dynamic height elements respects content flow is supported
> by legacy browsers

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch6-15">Section 6.15: Horizontal and Vertical centering using table layout</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

One could easily center a child element using table display property.

<h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;wrapper&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;parent&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;child&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.wrapper

{

**display**

:

table

;

**vertical-align**

:

center

;

**width**

:

200

px

;

**height**

:

200

px

;

**background-color**

:

#9e9e9e

;

}

.parent

{

**display**

:

table-cell

;

**vertical-align**

:

middle

;

**text-align**

:

center

;

}

.child

{

**display**

:

inline-block

;

**vertical-align**

:

middle

;

**text-align**

:

center

;

**width**

:

100

px

;

**height**

:

100

px

;

**background-color**

:

teal

;

}

# Chapter 7: The Box Model

**Parameter Detail**

> content-box Width and height of the element only includes content
> area. padding-box Width and height of the element includes content and
> padding. border-box Width and height of the element includes content,
> padding and border. initial Sets the box model to its default state.
> inherit Inherits the box model of the parent element.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch7-1">Section 7.1: What is the Box Model?</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>The Edges</h4>

> The browser creates a rectangle for each element in the HTML document.
> The Box Model describes how the padding, border, and margin are added
> to the content to create this rectangle.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 16.  (xx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image016.png"
  style="width:50%"
  title=""
  alt="." />
</p>
<!-- [image016.png](./images/image016.png)  <!-- 4.7" -->

Diagram from CSS2.2 Working Draft <a href="https://www.w3.org/TR/CSS22/box.html#mpb-examples">Demo</a>.

> The perimeter of each of the four areas is called an *edge*. Each edge
> defines a *box.*
>
> The innermost rectangle is the **content box**. The width and height
> of this depends on the element&apos;s rendered content (text, images and
> any child elements it may have).
>
> Next is the **padding box**, as defined by the padding property. If
> there is no padding width defined, the padding edge is equal to the
> content edge.
>
> Then we have the **border box**, as defined by the border property. If
> there is no border width defined, the border edge is equal to the
> padding edge.
>
> The outermost rectangle is the **margin box**, as defined by the
> margin property. If there is no margin width defined, the margin edge
> is equal to the border edge.
>
> **Example** div {

```
**border**: 5px solid red;
**margin**: 50px;
**padding**: 20px;
}
```

> This CSS styles all div elements to have a top, right, bottom and left
> border of 5px in width; a top, right, bottom and left margin of 50px;
> and a top, right, bottom, and left padding of 20px. Ignoring content,
> our generated box will look like this:
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 17.  (xx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image017.jpg"
  style="width:20%"
  title=""
  alt="." />
</p>
<!--[image017.jpg](./images/image017.jpg) <!-- 1.8" -->

> *Screenshot of Google Chrome&apos;s Element Styles panel*
>
> As there is no content, the content region (the blue box in the
> middle) has no height or width (0px by 0px). The padding box by
> default is the same size as the content box, plus the 20px width on
> all four edges we&apos;re defining above with the padding property (40px
> by 40px).
>
> The border box is the same size as the padding box, plus the 5px width
> we&apos;re defining above with the border property (50px by 50px).
>
> Finally the margin box is the same size as the border box, plus the
> 50px width we&apos;re defining above with the margin property (giving our
> element a total size of 150px by 150px).
>
> Now lets give our element a sibling with the same style. The browser
> looks at the Box Model of both elements to work out where in relation
> to the previous element&apos;s content the new element should be
> positioned:
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 18.  (xx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image018.jpg"
  style="width:30%"
  title=""
  alt="." />
</p>
<!-- [image018.jpg 3.6" width, 1.5" height](./images/image018.jpg) -->

> The content of each of element is separated by a 150px gap, but the
> two elements&apos; boxes touch each other.
>
> If we then modify our first element to have no right margin, the right
> margin edge would be in the same position as the right border edge,
> and our two elements would now look like this:
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 19.  (xx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image019.jpg"
  style="width:30%"
  title=""
  alt="." />
</p>
<!-- [image019.jpg 3.45" x 1.54"](./images/image019.jpg) -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch7-2">Section 7.2: box-sizing</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The default box model (content-box) can be counter-intuitive, since
> the width / height for an element will not represent its actual width
> or height on screen as soon as you start adding padding and border
> styles to the element.
>
> The following example demonstrates this potential issue with
> content-box:

```
textarea {
  <b>width</b>: 100&percnt;;
  <b>padding</b>: 3px;
  <b>box-sizing</b>: content-box; /* default value */
}
```

<p>Since the padding will be added to the width of the textarea, the
resulting element is a textarea that is wider than 100%.</p>

<p>Fortunately, CSS allows us to change the box model with the box-sizing
property for an element. There are three different values for the
property available:</p>

<ul>
  <li>content-box: The common box model - width and height only includes the
    content, not the padding or border.</li>
  <li>padding-box: Width and height includes the content and the padding, but 
    not the border.</li>
  <li>border-box: Width and height includes the content, the padding as well as 
    the border.</li>
</ul>

<image here>

<p>To solve the textarea problem above, you could just change the
box-sizing property to padding-box or borderbox. border-box is most
commonly used.</p>

```
textarea {
  <b>width</b>: 100&percnt;;
  <b>padding</b>: 3px;
  <b>box-sizing</b>: border-box;
}
```

<p>To apply a specific box model to every element on the page, use the following 
snippet:</p>

```
html {
  <b>box-sizing</b>: border-box;
}

&ast;, &ast;:before, &ast;:after {
  <b>box-sizing</b>: inherit;
}
```

<p>In this box-sizing: border-box; is not directly applied to &ast;, so you can easily
overwrite this property on individual elements.</p>

<h2 id="ch8">Chapter 8: Margins</h2>

| <b>Parameter</b>  | <b>Details</b> |
|-------------------|------------------------------------------------------------------|
| 0                 | set margin to none. |
| auto              | used for centering, by evenly setting values on each side units. |
| (e.g. px)         | see parameter section in Units for a list of valid units.
| inherit           | inherit margin value from parent element. 
| initial           | restore to initial value. |

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-1">Section 8.1: Margin Collapsing</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>When two margins are touching each other vertically, they are
collapsed. When two margins touch horizontally, they do not collapse.</p>

<h4>Example of adjacent vertical margins:</h4>

<p>Consider the following styles and markup:</p>

```
div {
  <b>margin</b>: 10px;
}

<b>&lt;div&gt;</b>
  some content
<b>&lt;/div&gt;</b>
<b>&lt;div&gt;</b>
  some more content
<b>&lt;/div&gt;</b>
```

<p>They will be 10px apart since vertical margins collapse over one and
other. (The spacing will not be the sum of two margins.)</p>

<h4>Example of adjacent horizontal margins:</h4>

<p>Consider the following styles and markup:</p>

```
span {
  <b>margin</b>: 10px;
}

<b>&lt;span&gt;</b>some<b>&lt;/span&gt;&lt;span&gt;</b>content<b>&lt;/span&gt;</b>
```

They will be 20px apart since horizontal margins don&apos;t collapse over
one and other. (The spacing will be the sum of two margins.)

<h4>Overlapping with different sizes</h4>

<pre><code>.top {
  <b>margin</b>: 10px;
}
.bottom {
 <b>margin</b>: 15px;
}
**&lt;****div** class = &quot;top&quot;**&gt;**
  some content
**&lt;****/div****&gt;**
**&lt;****div** class = &quot;bottom&quot;**&gt;**
  some more content
**&lt;****/div****&gt;**</code></pre>

> These elements will be spaced 15px apart vertically. The margins
> overlap as much as they can, but the larger margin will determine the
> spacing between the elements.
>
> **Overlapping margin gotcha**

<pre><code>.outer-top {
  **margin**: 10px;
}
.inner-top {
  **margin**: 15px;
}
.outer-bottom {
  **margin**: 20px;
}
.inner-bottom {
  **margin**: 25px;
}
**&lt;****div** class = &quot;outer-top&quot;**&gt;**
    **&lt;****div** class=&quot;inner-top&quot;**&gt;**
      some content
    **&lt;****/div****&gt;**
  **&lt;****/div****&gt;**
  **&lt;****div** class=&quot;outer-bottom&quot;**&gt;**
    **&lt;****div** class=&quot;inner-bottom&quot;**&gt;**
      some more content
  **&lt;****/div****&gt;**
**&lt;****/div****&gt;**</code></pre>

> What will be the spacing between the two texts? (hover to see answer)
>
> The spacing will be 25px. Since all four margins are touching each
> other, they will collapse, thus using the largest margin of the four.
>
> Now, what about if we add some borders to the markup above.

<pre><code>div {
  **border**: 1px solid red;
}</code></pre>

> What will be the spacing between the two texts? (hover to see answer)
>
> The spacing will be 59px! Now only the margins of .outer-top and
> .outer-bottom touch each other, and are the only collapsed margins.
> The remaining margins are separated by the borders. So we have 1px +
>
> 10px + 1px + 15px + 20px + 1px + 25px + 1px. (The 1px&apos;s are the
> borders&period;..)
>
> **Collapsing Margins Between Parent and Child Elements:**
>
<h4>HTML:</h4>

<pre><code.**&lt;****h****1****&gt;**Title**&lt;****/h****1****&gt;**
**&lt;****div****&gt;**
  **&lt;****p****&gt;**Paragraph**&lt;****/p****&gt;**
**&lt;****/div****&gt;**</code></pre>


<h4>CSS:</h4>

<pre><code>h1 {
  **margin**: 0;
  **background**: #cff;
}
  div {
  **margin**: 50px 0 0 0;
  **background**: #cfc;
}
  p {
  **margin**: 25px 0 0 0;
  **background**: #cf9;
}</code></pre>

> In the example above, only the largest margin applies. You may have
 expected that the paragraph would be located 60px from the h1 (since
> the div element has a margin-top of 40px and the p has a 20px
> margin-top). This does not happen because the margins collapse
> together to form one margin.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-2">Section 8.2: Apply Margin on a Given Side</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>Direction-Specific Properties</h4>

CSS allows you to specify a given side to apply margin to. The four
properties provided for this purpose are:

<ul>
  <li>margin-left</li>
  <li>margin-right</li>
  <li>margin-top</li>
  <li>margin-bottom</li>
</ul>

The following code would apply a margin of 30 pixels to the left side
of the selected div. <a href="https://jsfiddle.net/wm0100x9/1/">View Result</a>.

<h4>HTML</h4>

```
**&lt;****div** id=&quot;myDiv&quot;**&gt;****&lt;****/div****&gt;**
```

<h4>CSS:</h4>

```
#myDiv {
  **margin-left**: 30px;
  **height**: 40px;
  **width**: 40px;
  **background-color**: red;
}
```

| <b>Parameter</b> | <b>Details</b> |
|------------------|-------------------------------------------------|
| margin-left | The direction in which the margin should be applied. |
| 30px | The width of the margin. |

<h4>Specifying Direction Using Shorthand Property</h4>

The standard margin property can be expanded to specify differing
widths to each side of the selected elements. The syntax for doing
this is as follows:

```
**margin**: &lt;top&gt; &lt;right&gt; &lt;bottom&gt; &lt;left&gt;;
```

> The following example applies a zero-width margin to the top of the
> div, a 10px margin to the right side, a 50px margin to the left side,
> and a 100px margin to the left side. <a href="https://jsfiddle.net/1979c947/">View
> Result.
>
<h4>HTML</h4>

```
**&lt;****div**id=&quot;myDiv&quot;**&gt;****&lt;****/div****&gt;**
```

<h4>CSS</h4>

```
#myDiv {
  **margin**: 0 10px 50px 100px;
  **height**: 40px;
  **width**: 40px;
  **background-color**: red;
}
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-3">Section 8.3: Margin property simplification</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
p {
  **margin**: 1px; /* 1px margin in all directions */

  /* equals to: */
  **margin**: 1px 1px;

  /* equals to: */
  **margin**: 1px 1px 1px;

  /* equals to: */
  **margin**: 1px 1px 1px 1px;
}
```

> Another exapmle:

<pre><code>p {
  **margin**: 10px 15px; /* 10px margin-top & bottom And 15px margin-right & left */

  /* equals to: */
  **margin**: 10px 15px 10px 15px;

  /* equals to: */
  **margin**: 10px 15px 10px;

  /* margin left will be calculated from the margin right value (=15px) */
}</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-4">Section 8.4: Horizontally center elements on a page using margin</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> As long as the element is a **block**, and it has an **explicitly set
> width value**, margins can be used to center block elements on a page
> horizontally.
>
> We add a width value that is lower than the width of the window and
> the auto property of margin then distributes the remaining space to
> the left and the right:

```
#myDiv {
  **width**:80&percnt;;
  **margin**:0 auto;
}
```

> In the example above we use the shorthand margin declaration to first
> set 0 to the top and bottom margin values (although this could be any
> value) and then we use auto to let the browser allocate the space
> automatically to the left and right margin values.
>
> In the example above, the #myDiv element is set to 80% width which
> leaves use 20% leftover. The browser distributes this value to the
> remaining sides so:

```
(100% - 80%) / 2 = 10%
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-5">Section 8.5: Example 1:</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

It is obvious to assume that the percentage value of margin to
margin-left and margin-right would be relative to its parent element.

```
.parent {
  **width**: 500px;
  **height**: 300px;
}
.child {
  **width**: 100px;
  **height**: 100px;
  **margin-left**: 10&percnt;; /* (parentWidth &ast; 10/100) =&gt; 50px */
}
```

> But that is not the case, when comes to margin-top and margin-bottom.
> Both these properties, in percentages, aren&apos;t relative to the height
> of the parent container but to the **width** of the parent container.
>
> So,

<pre><code>.parent {
  <b>width</b>: 500px;
  <b>height</b>: 300px;
}
.child {
  <b>width</b>: 100px;
  <b>height</b>: 100px;
  <b>margin-left</b>: 10&percnt;;  /* (parentWidth &ast; 10/100) =&gt; 50px */
  <b>margin-top</b>: 20&percnt;;  /* (parentWidth &ast; 20/100) =&gt; 100px */
}</code></pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch8-6">Section 8.6: Negative margins</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Margin is one of a few CSS properties that can be set to negative
values. This property can be used to <b>overlap elements without
absolute positioning</b>.</p>

<pre><code>div {
  **display**: inline;
}
#over {
  **margin-left**: -20px;
}
&lt;div&gt;Base div&lt;/div&gt;
&lt;div id=&quot;over&quot;&gt;Overlapping div&lt;/div&gt;</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch9">Chapter 9: Padding</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch9-1">Section 9.1: Padding Shorthand</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The padding property sets the padding space on all sides of an
> element. The padding area is the space between the content of the
> element and its border. Negative values are not allowed.
>
> To save adding padding to each side individually (using padding-top,
> padding-left etc) can you write it as a shorthand, as below:
>

<h4>Four values:</h4>

```
**&lt;**
**style**
**&gt;**
.myDiv {
padding: 25px 50px 75px 100px; /&ast; top right bottom left; &ast;/
}
**&lt;**
**/style**
**&gt;**
**&lt;**
**div**
class
=
&quot;myDiv&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
```

<h4>Three values:</h4>

```
**&lt;**
**style**
**&gt;**
.myDiv
{
padding: 25px 50px 75px; /&ast; top left/right bottom &ast;/
}
**&lt;**
**/style**
**&gt;**
**&lt;**
**div**
class
=
&quot;myDiv&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
```

</h4>Two values:</h4>

```
**&lt;**
**style**
**&gt;**
.myDiv
{
padding: 25px 50px; /&ast; top/bottom left/right &ast;/
}
**&lt;**
**/style**
**&gt;**
**&lt;**
**div**
class
=
&quot;myDiv&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
```

<h4>One value:</h4>

```
**&lt;**
**style**
**&gt;**
.myDiv
{
padding: 25px; /&ast; top/right/bottom/left &ast;/
}
**&lt;**
**/style**
**&gt;**
**&lt;**
**div**
class
=
&quot;myDiv&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch9-2">Section 9.2: Padding on a given side</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

The padding property sets the padding space on all sides of an
element. The padding area is the space between the content of the
element and its border. Negative values are not allowed.

You can specify a side individually:

<ul>
  <li>padding-top </li>
  <li>padding-right</li>
  <li>padding-bottom</li>
  <li>padding-left</li>
</ul>

The following code would add a padding of 5px to the top of the div:

<pre><code>**&lt;****style****&gt;**
  .myClass {
    padding-top: 5px;
}
**&lt;****/style****&gt;**
**&lt;****div** class=&quot;myClass&quot;**&gt;****&lt;****/div****&gt;**</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch10">Chapter 10: Border</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-1">Section 10.1: border-radius</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The border-radius property allows you to change the shape of the basic
> box model.
>
> Every corner of an element can have up to two values, for the vertical
> and horizontal radius of that corner (for a maximum of 8 values).
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 25.  (xx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image025.jpg"
  style="width:60%"
  title=""
  alt="." />
</p>
<!-- [image025.jpg 6.14 x 1.93](./images/image025.jpg) -->

> The first set of values defines the horizontal radius. The optional
> second set of values, preceded by a '/' , defines the vertical radius.
> If only one set of values is supplied, it is used for both the
> vertical and horizontal radius.

```
**border-radius**: 10px 5&percnt; / 20px 25em 30px 35em;
```

> The 10px is the horizontal radius of the top-left-and-bottom-right.
> And the 5% is the horizontal radius of the topright-and-bottom-left.
> The other four values after &apos;/&apos; are the vertical radii for top-left,
> top-right, bottom-right and bottom-left.
>
> As with many CSS properties, shorthands can be used for any or all
> possible values. You can therefore specify anything from one to eight
> values. The following shorthand allows you to set the horizontal and
> vertical radius of every corner to the same value:
>

<h4>HTML:</h4>

```
**&lt;**
**div**
class
=
&apos;box&apos;
**&gt;**
**&lt;**
**/div**
**&gt;**
```

<h4>CSS:</h4>

```
.box {
  **width**: 250px;
  **height**: 250px;
  **background-color**: black;
  **border-radius**: 10px;
}
```

> Border-radius is most commonly used to convert box elements into
> circles. By setting the border-radius to half of the length of a
> square element, a circular element is created:

```
.circle {
  **width**: 200px;
  **height**: 200px;
  **border-radius**: 100px;
}
```

> Because border-radius accepts percentages, it is common to use 50% to
> avoid manually calculating the borderradius value:

```
.circle {
  **width**: 150px;
  **height**: 150px;
  **border-radius**: 50&percnt;;
}
```

> If the width and height properties are not equal, the resulting shape
> will be an oval rather than a circle.
>

<h4>Browser specific border-radius example:</h4>

```
-webkit-border-top-right-radius: 4px;
-webkit-border-bottom-right-radius: 4px;
-webkit-border-bottom-left-radius: 0;
-webkit-border-top-left-radius: 0;
-moz-border-radius-topright: 4px;
-moz-border-radius-bottomright: 4px;
-moz-border-radius-bottomleft: 0;
-moz-border-radius-topleft: 0;

  **border-top-right-radius**: 4px;
  **border-bottom-right-radius**: 4px;
  **border-bottom-left-radius**: 0;
  **border-top-left-radius**: 0;
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-2">Section 10.2: border-style</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The border-style property sets the style of an element&apos;s border. This
> property can have from one to four values (for every side of the
> element one value.) Examples:

```
**border-style**: dotted;
**border-style**: dotted solid double dashed;
```

> border-style can also have the values none and hidden. They have the
> same effect, except hidden works for <b>&lt;table&gt;</b> elements. In a
> <b>&lt;table&gt;</b> with multiple borders, none has the lowest priority 
> (meaning in a conflict, the border would show), and hidden has the
> highest priority (meaning in a conflict, the border would not show).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-3">Section 10.3: Multiple Borders</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Using outline:

```
.div1
{
**border**
:
3
px
solid
black
;
**outline**
:
6
px
solid
blue
;
**width**
:
100
px
;
**height**
:
100
px
;
**margin**
:
20
px
;
}
```

> Using box-shadow:

```
.div2 {

**border**

:

5

px

solid

green

;

**box-shadow**

:

0

px

0

px

0

px

4

px

#000

;

**width**

:

100

px

;

**height**

:

100

px

;

**margin**

:

20

px

;

}
```

> Using a pseudo element:

```
.div3 {
  **position**: relative;
  **border**: 5px solid #000;
  **width**: 100px;
  **height**: 100px;
  **margin**: 20px;
}
.div3:before {
  **content**: &quot; &quot;;
  **position**: absolute;
  **border**: 5px solid blue;
  **z-index**: &minus;1;
  **top**: 5px;
  **left**: 5px;
  **right**: 5px;
  **bottom**: 5px;
}
```
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 27.  (xx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image027.jpg"
  style="width:20%"
  title=""
  alt="." />
</p>
<!-- [image027.jpg 1.458 x 4.021](./images/image027.jpg) -->

<a href="http://jsfiddle.net/MadalinaTn/bvqpcohm/2/&rbrack;&rbrack;(http://jsfiddle.net/MadalinaTn/bvqpcohm/2/">jsFiddle Demo</a>.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-4">Section 10.4: border (shorthands)</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> In most cases you want to define several border properties
> (border-width, border-style and border-color) for all sides of an
> element.
>
> Instead of writing:

**border-width**

:

1

px

;

**border-style**

:

solid

;

**border-color**

:

#000

;

> You can simply write:

**border**

:

1

px

solid

#000

;

> These shorthands are also available for every side of an element:
> border-top, border-left, border-right and border-bottom. So you can
> do:

**border-top**

:

2

px

double

#aaaaaa

;

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-5">Section 10.5: border-collapse</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

  **display**                         :     table

> The border-collapse property applies only to tables (and elements
> displayed as or inlinetable) and sets whether the table borders are
> collapsed into a single border or detached as in standard HTML.

table

{

**border-collapse**

:

separate

;

*/&ast; default &ast;/*

**border-spacing**

:

2

px

;

*/&ast; Only works if border-collapse is separate &ast;/*

}

> Also see Tables - border-collapse documentation entry

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-6">Section 10.6: border-image</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> With the border-image property you have the possibility to set an
> image to be used instead of normal border styles.
>
> A border-image essentially consist of a
>
> border-image-source: The path to the image to be used
> border-image-slice: Specifies the offset that is used to divide the
> image into **nine regions** (four **corners**, four **edges** and a
> **middle**)
>
> border-image-repeat: Specifies how the images for the sides and the
> middle of the border image are scaled
>
> Consider the following example wheras border.png is a image of 90x90
> pixels:

  **border-image**     :   url    (   &quot;border.png&quot;       )   30 stretch

> ;
>
> The image will be split into nine regions with 30x30 pixels. The edges
> will be used as the corners of the border while the side will be used
> in between. If the element is higher / wider than 30px this part of
> the image will be **stretched**. The middle part of the image defaults
> to be transparent.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-7">Section 10.7: Creating a multi-colored border using borderimage</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>CSS</h4>

```
.bordered
{
**border-image**
:
linear-gradient
(
to
right
,
red
20
&percnt;
,
green
20
&percnt;
,
green
40
&percnt;
,
blue
40
&percnt;
,
blue
60
&percnt;
,
maroon
60
&percnt;
,
maroon
80
&percnt;
,
chocolate
80
&percnt;
)
;
*/&ast; gradient with required colors &ast;/*
**border-image-slice**
:
1
;
}
```

<h4>HTML</h4>

```
**&lt;**
**div**
class
=
&apos;bordered&apos;
**&gt;**
Border on all sides
**&lt;**
**/div**
**&gt;**
```

> The above example would produce a border that comprises of 5 different
> colors. The colors are defined through a linear-gradient (you can find
> more information about gradients in the docs). You can find more
> information about border-image-slice property in the border-image
> example in same page.

[image028.jpg 3.5"x1.437"](./images/image028.jpg)

> (*Note: Additional properties were added to the element for
> presentational purpose.*)
>
> You&apos;d have noticed that the left border has only a single color (the
> start color of the gradient) while the right border also has only a
> single color (the gradient&apos;s end color). This is because of the way
> that border image property works. It is as though the gradient is
> applied to the entire box and then the colors are masked from the
> padding and content areas, thus making it look as though only the
> border has the gradient.

  to right

  to bottom

> Which border(s) have a single color is dependant on the gradient
> definition. If the gradient is a gradient, the left border would be
> the start color of the gradient and right border would be the end
> color. If it was a to bottom gradient the top border would be the
> gradient&apos;s start color and bottom border would be end color. Below is
> the output of a 5 colored gradient.

[image029.jpg 3.489 x 1.40](./images/image029.jpg)

> If the border is required only on specific sides of the element then
> the border-width property can be used just like with any other normal
> border. For example, adding the below code would produce a border only
> on the top of the element.

**border-width**

:

5

px

0

px

0

px

0

px

;

> Note that, any element that has border-image property **won&apos;t respect
> the** border-radius (that is the border won&apos;t curve). This is based
> on the below statement in the spec:
>
> A box&apos;s backgrounds, but not its border-image, are clipped to the
> appropriate curve (as determined by 'background-clip').

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch10-8">Section 10.8: border-&lbrack;left&vertbar;right&vertbar;top&vertbar;bottom&rbrack;</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

  border-           &lbrack;   left      &vertbar;   right        &vertbar;   top     &vertbar;   bottom


> The &rbrack; property is used to add a border to a specific side of an
> element.
>
> For example if you wanted to add a border to the left side of an
> element, you could do:

&num;

element

{

**border-left**

:

1

px

solid

black

;

}

<h2 id="ch11">Chapter 11: Outlines</h2>

**Parameter Details**

  dotted       dotted outline

  dashed       dashed outline

  solid        solid outline

  double       double outline

  groove       3D grooved outline, depends on the outline-color value

  ridge        3D ridged outline, depends on the outline-color value

  inset        3D inset outline, depends on the outline-color value

  outset       3D outset outline, depends on the outline-color value

  none         no outline

  hidden       hidden outline

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch11-1">Section 11.1: Overview</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Outline is a line that goes around the element, outside of the border.
> In contrast to border, outlines do not take any space in the box
> model. So adding an outline to an element does not affect the position
> of the element or other elements.
>
> In addition, outlines can be non-rectangular in some browsers. This
> can happen if outline is applied on a span element that has text with
> different font-size properties inside it. Unlike borders, outlines
> *cannot* have rounded corners.
>
> The essential parts of outline are outline-color, outline-style and
> outline-width.
>
> The definition of an outline is equivalent to the definition of a
> border:

An outline is a line around an element. It is displayed around the
margin of the element. However, it is

different from the border property.

**outline**

:

1

px

solid

black

;

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch11-2">Section 11.2: outline-style</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The outline-style property is used to set the style of the outline of
> an element.

p

{

**border**

:

1

px

solid

black

;

**outline-color**

:

blue

;

**line-height**

:

30

px

;

}

.p1

{

**outline-style**

:

dotted

;

}

.p2

{

**outline-style**

:

dashed

;

}

.p3

{

**outline-style**

:

solid

;

}

.p4

{

**outline-style**

:

double

;

}

.p5

{

**outline-style**

:

groove

;

}

.p6

{

**outline-style**

:

ridge

;

}

.p7

{

**outline-style**

:

inset

;

}

.p8

{

**outline-style**

:

outset

;

}

> <h4>HTML</h4>

**&lt;**

**p**

class

=

&quot;p1&quot;

**&gt;**

A dotted outline

**&lt;**

**/p**

**&gt;**

**&lt;**

**p**

class

=

&quot;p2&quot;

**&gt;**

A dashed outline

**/p**

**&lt;**

**&gt;**

**&lt;**

**p**

class

=

&quot;p3&quot;

**&gt;**

A solid outline

**&lt;**

**/p**

**&gt;**

**&lt;**

**p**

class

=

&quot;p4&quot;

**&gt;**

A double outline

**/p**

**&lt;**

**&gt;**

**&lt;**

**p**

class

=

&quot;p5&quot;

**&gt;**

A groove outline

**/p**

**&lt;**

**&gt;**

**&lt;**

**p**

class

=

&quot;p6&quot;

**&gt;**

A ridge outline

**/p**

**&lt;**

**&gt;**

**&lt;**

**p**

class

=

&quot;p7&quot;

**&gt;**

An inset outline

**&lt;**

**/p**

**&gt;**

**&lt;**

**p**

class

=

&quot;p8&quot;

**&gt;**

An outset outline

**&lt;**

**/p**

**&gt;**

<h2 id="ch12">Chapter 12: Overflow</h2>

**Overflow Value Details**

  visible     Shows all overflowing content outside the element
  scroll      Hides the overflowing content and adds a scroll bar

  hidden      Hides the overflowing content, both scroll bars disappear
              and the page becomes fixed

  auto        Same as scroll if content overflows, but doesn&apos;t add
              scroll bar if content fits

  inherit     Inherit&apos;s the parent element&apos;s value for this property

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch12-1">Section 12.1: overflow-wrap</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> overflow-wrap tells a browser that it can break a line of text inside
> a targeted element onto multiple lines in an otherwise unbreakable
> place. Helpful in preventing an long string of text causing layout
> problems due to overflowing it&apos;s container.
>
> <h4>CSS</h4>

div

{

**width**

:

100

px

;

**outline**

:

1

px

dashed

#bbb

;

}

#div1

{

**overflow-wrap**

:

normal

;

}

#div2

{

**overflow-wrap**

:

break-word

;

}

<h4>HTML</h4>

**&lt;**

**div**

id

=

&quot;div1&quot;

**&gt;**

**&lt;**

**strong**

**&gt;**

#div1

**&lt;**

**/strong**

**&gt;**

:

Small words are displayed normally, but a long word like

**&lt;**

**span**

style

=

&quot;red;&quot;

**&gt;**

supercalifragilisticexpialidocious

**&lt;**

**/span**

**&gt;**

is too long so it will overflow past the

edge of the line-break

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

id

=

&quot;div2&quot;

**&gt;**

**&lt;**

**strong**

**&gt;**

#div2

**&lt;**

**/strong**

**&gt;**

:

Small words are displayed normally, but a long word like

**&lt;**

**span**

style

=

&quot;red;&quot;

**&gt;**

supercalifragilisticexpialidocious

**&lt;**

**/span**

**&gt;**

will be split at the line break and continue

on the next line.

**&lt;**

**/div**

**&gt;**

[image032.jpg 7.48 x 4.27](./images/image032.jpg)

**overflow-wrap** -- **Value Details**

> normal Lets a word overflow if it is longer than the line break-word
> Will split a word into multiple lines, if necessary inherit Inherits
> the parent element&apos;s value for this property

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch12-2">Section 12.2: overflow-x and overflow-y</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> These two properties work in a similar fashion as the overflow
> property and accept the same values. The overflow-x parameter works
> only on the x or left-to-right axis. The overflow-y works on the y or
> top-to-bottom axis.
>
<h4>HTML</h4>

**&lt;**

**div**

id

=

&quot;div-x&quot;

**&gt;**

If this div is too small to display its contents,

the content to the left and right will be clipped.

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

id

=

&quot;div-y&quot;

**&gt;**

If this div is too small to display its contents,

the content to the top and bottom will be clipped.

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

div

{

**width**

:

200

px

;

**height**

:

200

px

;

}

#div-x

{

**overflow-x**

:

hidden

;

}

#div-y

{

**overflow-y**

:

hidden

;

}
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch12-3">Section 12.3: overflow: scroll</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML</h4>

**&lt;**

**div**

**&gt;**

This div is too small to display its contents to display the effects of
the overflow property.

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

div

{

**width**

:

100

px

;

**height**

:

100

px

;

**overflow**

:

scroll

;

}

> **Result**

[image033.jpg 1.16 x 1.18](./images/image033.jpg)

> The content above is clipped in a 100px by 100px box, with scrolling
> available to view overflowing content.
>
> Most desktop browsers will display both horizontal and vertical
> scrollbars, whether or not any content is clipped. This can avoid
> problems with scrollbars appearing and disappearing in a dynamic
> environment. Printers may print overflowing content.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch12-4">Section 12.4: overflow: visible</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML</h4>

**&lt;**

**div**

**&gt;**

Even if this div is too small to display its contents, the content is
not clipped.

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

div

{

**width**

:

50

px

;

**height**

:

50

px

;

**overflow**

:

visible

;

}

> **Result**

[image034.jpg .67 x 2.427](./images/image034.jpg)

> Content is not clipped and will be rendered outside the content box if
> it exceeds its container size.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch12-5">Section 12.5: Block Formatting Context Created with Overflow</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Using the overflow property with a value different to visible will
> create a new **block formatting context**. This is useful for aligning
> a block element next to a floated element.
>
<h4>CSS</h4>

img

{

**float**

:

left

;

**margin-right**

:

10

px

;

}

div

{

**overflow**

:

hidden

;

*/&ast; creates block formatting context &ast;/*

}

> <h4>HTML</h4>

**&lt;**

**img**

src

=

&quot;http://placehold.it/100x100&quot;

**&gt;**

**&lt;**

**div**

**&gt;**

**&lt;**

**p**

**&gt;**

Lorem ipsum dolor sit amet, cum no paulo mollis pertinacia.

**&lt;**

**/p**

**&gt;**

**&lt;**

**p**

**&gt;**

Ad case omnis nam, mutat deseruisse persequeris eos ad, in tollit
debitis sea.

**&lt;**

**/p**

**&gt;**

**&lt;**

**/div**

**&gt;**

> **Result**

[imge035.jpg 6.375 x 3.76](./images/image035.jpg)

> This example shows how paragraphs within a div with the overflow
> property set will interact with a floated image.

<h2 id="ch12">Chapter 13: Media Queries</h2>

| **          | > **Details**                                          |
|-------------|--------------------------------------------------------|
| Parameter** |                                                        |
| mediatype   | (Optional) This is the type of media. Could be         |
|             | anything in the range of all to screen.                |
|-------------|--------------------------------------------------------|
| not         | (Optional) Doesn&apos;t apply the CSS for this particular  |
|             | media type and applies for everything else.            |
|-------------|--------------------------------------------------------|
| media       | Logic to identify use case for CSS. Options outlined   |
| feature     | below.                                                 |
|-------------|--------------------------------------------------------|
| **Media     | **Details**                                            |
| Feature**   |                                                        |
|-------------|--------------------------------------------------------|
| a           | Describes the aspect ratio of the targeted display     |
| spect-ratio | area of the output device.                             |
|-------------|--------------------------------------------------------|
| color       | Indicates the number of bits per color component of    |
|             | the output device. If the device is not a color        |
|             | device, this value is zero.                            |
|-------------|--------------------------------------------------------|
| color-index | Indicates the number of entries in the color look-up   |
|             | table for the output device.                           |
|-------------|--------------------------------------------------------|
| grid        | Determines whether the output device is a grid device  |
|             | or a bitmap device.                                    |
|-------------|--------------------------------------------------------|
| height      | The height media feature describes the height of the   |
|             | output device&apos;s rendering surface.                    |
|-------------|--------------------------------------------------------|
| max-width   | CSS will not apply on a screen width wider than        |
|             | specified.                                             |
|-------------|--------------------------------------------------------|
| min-width   | CSS will not apply on a screen width narrower than     |
|             | specified.                                             |
|-------------|--------------------------------------------------------|
| max-height  | CSS will not apply on a screen height taller than      |
|             | specified.                                             |
|-------------|--------------------------------------------------------|
| min-height  | CSS will not apply on a screen height shorter than     |
|             | specified.                                             |
|-------------|--------------------------------------------------------|
| monochrome  | Indicates the number of bits per pixel on a monochrome |
|             | (greyscale) device.                                    |
|-------------|--------------------------------------------------------|
| orientation | CSS will only display if device is using specified     |
|             | orientation. See remarks for more details.             |
|-------------|--------------------------------------------------------|
| resolution  | Indicates the resolution (pixel density) of the output |
|             | device.                                                |
|-------------|--------------------------------------------------------|
| scan        | Describes the scanning process of television output    |
|             | devices.                                               |
|-------------|--------------------------------------------------------|
| width       | The width media feature describes the width of the     |
|             | rendering surface of the output device (such as the    |
|             | width of the document window, or the width of the page |
|             | box on a printer).                                     |
|-------------|--------------------------------------------------------|

> **Deprecated Features Details**
>
> **Deprecated** CSS will only display on devices whose height/width
> ratio matches the specified
>
> device-aspect-ratio ratio. This is adeprecatedfeature and is not
> guaranteed to work.
>
> **Deprecated** Same as max-width but measures the physical screen
> width, rather than the
>
> max-device-width display width of the browser.
>
> **Deprecated** Same as min-width but measures the physical screen
> width, rather than the
>
> min-device-width display width of the browser.
>
> **Deprecated** Same as max-height but measures the physical screen
> width, rather than the
>
> max-device-height display width of the browser.
>
> **Deprecated** Same as min-height but measures the physical screen
> width, rather than the
>
> min-device-height
>
> display width of the browser.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-1">Section 13.1: Terminology and Structure</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> **Media queries** allow one to apply CSS rules based on the type of
> device / media (e.g. screen, print or handheld) called **media type**,
> additional aspects of the device are described with **media features**
> such as the availability of color or viewport dimensions.
>
> **General Structure of a Media Query**

**&commat;media**

&lbrack;

&period;..

&rbrack;

{

*/&ast; One or more CSS rules to apply when the query is satisfied &ast;/*

}

> **A Media Query containing a Media Type**

**&commat;media**

print

{

*/&ast; One or more CSS rules to apply when the query is satisfied &ast;/*

}

**A Media Query containing a Media Type and a Media Feature**

**&commat;media**

screen and

(

**max-width**

:

600

px

)

{

*/&ast; One or more CSS rules to apply when the query is satisfied &ast;/*

}

**A Media Query containing a Media Feature (and an implicit Media Type
of &quot;all&quot;)**

**&commat;media**

(

orientation

:

portrait

)

{

*/&ast; One or more CSS rules to apply when the query is satisfied &ast;/*

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-2">Section 13.2: Basic Example</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

**&commat;media**

screen and

(

**min-width**

:

720

px

)

{

body

{

**background-color**

:

skyblue

;

}

}

> The above media query specifies two conditions:

1.  The page must be viewed on a normal screen (not a printed page,
    projector, etc).

2.  The width of the user&apos;s view port must be at least 720 pixels.

> If these conditions are met, the styles inside the media query will be
> active, and the background color of the page will be sky blue.
>
> Media queries are applied dynamically. If on page load the conditions
> specified in the media query are met, the CSS will be applied, but
> will be immediately disabled should the conditions cease to be met.
> Conversely, if the conditions are initially not met, the CSS will not
> be applied until the specified conditions are met.
>
> In our example, if the user&apos;s view port width is initially greater
> than 720 pixels, but the user shrinks the browser&apos;s width, the
> background color will cease to be sky blue as soon as the user has
> resized the view port to less than 720 pixels in width.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-3">Section 13.3: mediatype</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

  **&commat;media** mediatype

> Media queries have an optional mediatype parameter. This parameter is
> placed directly after the &commat;media declaration (), for example:

**&commat;media**

print

{

html

{

**background-color**

:

white

;

}

}

> The above CSS code will give the DOM HTML element a white background
> color when being printed.
>
> The mediatype parameter has an optional not or only prefix that will
> apply the styles to everything except the specified mediatype *or*
> only the specified media type, respectively. For example, the
> following code example will apply the style to every media type except
> print.

**&commat;media**

not

print

{

html

{

**background-color**

:

green

;

}

}

> And the same way, for just showing it only on the screen, this can be
> used:

**&commat;media**

only screen

{

.fadeInEffects

{

**display**

:

block

;

}

}

> The list of mediatype can be understood better with the following
> table:

**Media Type Description**

> all Apply to all devices screen Default computers
>
> print Printers in general. Used to style print-versions of websites
> handheld PDA&apos;s, cellphones and hand-held devices with a small screen
> projection For projected presentation, for example projectors

aural Speech Systems

> braille Braille tactile devices embossed Paged braille printers tv
> Television-type devices tty Devices with a fixed-pitch character grid.
> Terminals, portables.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch13-4">Section 13.4: Media Queries for Retina and Non Retina Screens</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Although this works only for WebKit based browsers, this is helpful:

/* Non-Retina Screens */

**&commat;media**

screen

and

(

**min-width**

:

1200

px

)

and

(

**max-width**

:

1600

px

)

and

(

&minus;

webkit-min-device-pixel-ratio

:

1

)

{

}

*/&ast; &minus;&minus;&minus;&minus;&minus;&minus;&minus;&minus;&minus;&minus;- Retina Screens &minus;&minus;&minus;&minus;&minus;&minus;&minus;&minus;&minus;&minus;- &ast;/*

**&commat;media**

screen

and

(

**min-width**

:

1200

px

)

and

(

**max-width**

:

1600

px

)

and

(

&minus;

webkit-min-device-pixel-ratio

:

2

)

and

(

min-resolution

:

192

dpi

)

{

}

> **Background Information**
>
> There are two types of pixels in the display. One is the logical
> pixels and the other is the physical pixels. Mostly, the physical
> pixels always stay the same, because it is the same for all the
> display devices. The logical pixels change based on the resolution of
> the devices to display higher quality pixels. The device pixel ratio
> is the ratio between physical pixels and logical pixels. For instance,
> the MacBook Pro Retina, iPhone 4 and above report a device pixel ratio
> of 2, because the physical linear resolution is double the logical
> resolution.
>
> The reason why this works only with WebKit based browsers is because
> of:
>
> The vendor prefix -webkit- before the rule.
>
> This hasn&apos;t been implemented in engines other than WebKit and Blink.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 13.5: Width vs Viewport
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

  **&lt;head**

> When we are using &quot;width&quot; with media queries it is important to set
> the meta tag correctly. Basic meta tag looks like this and it needs to
> be put inside the **&gt;** tag.
>
> **&lt;meta** name=&quot;viewport&quot;
> content=&quot;width=device-width,initial-scale=1&quot;**&gt;**
>
> **Why this is important?**
>
> Based on MDN&apos;s definition &quot;width&quot; is
>
> The width media feature describes the width of the rendering surface
> of the output device (such as the width of the document window, or the
> width of the page box on a printer).
>
> What does that mean?
>
> View-port is the width of the device itself. If your screen resolution
> says the resolution is 1280 x 720, your view-port width is &quot;1280px&quot;.
>
> More often many devices allocate different pixel amount to display one
> pixel. For an example iPhone 6 Plus has 1242 x 2208 resolution. But
> the actual viewport-width and viewport-height is 414 x 736. That means
> 3 pixels are used to create 1 pixel.
>
> But if you did not set the meta tag correctly it will try to show your
> webpage with its native resolution which results in a zoomed out view
> (smaller texts and images).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 13.6: Using Media Queries to Target Dierent Screen Sizes0
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Often times, responsive web design involves media queries, which are
> CSS blocks that are only executed if a condition is satisfied. This is
> useful for responsive web design because you can use media queries to
> specify different CSS styles for the mobile version of your website
> versus the desktop version.

**&commat;media**

only screen and

(

**min-width**

:

300

px

)

and

(

**max-width**

:

767

px

)

{

.site-title

{

**font-size**

:

80

&percnt;

;

}

*/&ast; Styles in this block are only applied if the screen size is atleast
300px wide, but no more*

*than 767px &ast;/*

}

**&commat;media**

only screen and

(

**min-width**

:

768

px

)

and

(

**max-width**

:

1023

px

)

{

.site-title

{

**font-size**

:

90

&percnt;

;

}

*/&ast; Styles in this block are only applied if the screen size is atleast
768px wide, but no more*

*than 1023px &ast;/*

}

**&commat;media**

only screen and

(

**min-width**

:

1024

px

)

{

.site-title

{

**font-size**

:

120

&percnt;

;

}

*/&ast; Styles in this block are only applied if the screen size is over
1024px wide. &ast;/*

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 13.7: Use on link tag
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> **&lt;link** rel=&quot;stylesheet&quot; media=&quot;min-width: 600px&quot;
> href=&quot;example.css&quot; **/&gt;**
>
> This stylesheet is still downloaded but is applied only on devices
> with screen width larger than 600px.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 13.8: Media queries and IE8
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> &lbrack;**&lbrack;Media
> queries&rbrack;**&rbrack;(http://www.brianhadaway.com/responsive-web-design-using-css3-media-queries/)
> are not supported at all in IE8 and below.
>
> **A Javascript based workaround**
>
> To add support for IE8, you could use one of several JS solutions. For
> example,
> &lbrack;**&lbrack;Respond&rbrack;**&rbrack;(https://github.com/scottjehl/Respond) can
> be added to add media query support for IE8 only with the following
> code :

&lt;!&minus;-

&lbrack;

if lt IE 9

&rbrack;

**&gt;**

**&lt;**

**script**

src

=

&quot;respond.min.js&quot;

**&gt;**

**&lt;**

**/script**

**&gt;**

&lt;!

&lbrack;

endif

&rbrack;

&minus;-

**&gt;**

> &lbrack;**&lbrack;CSS
> Mediaqueries&rbrack;**&rbrack;(https://code.google.com/p/css3-mediaqueries-js/)
> is another library that does the same thing. The code for adding that
> library to your HTML would be identical :

&lt;!&minus;-

&lbrack;

if lt IE 9

&rbrack;

**&gt;**

**&lt;**

**script**

src

=

&quot;css3-mediaqueries.js&quot;

**&gt;**

**&lt;**

**/script**

**&gt;**

&lt;!

&lbrack;

endif

&rbrack;

&minus;-

**&gt;**

> **The alternative**
>
> If you don&apos;t like a JS based solution, you should also consider
> adding an IE&lt;9 only stylesheet where you adjust your styling specific
> to IE&lt;9. For that, you should add the following HTML to your code:

&lt;!&minus;-

&lbrack;

if lt IE 9

&rbrack;

**&gt;**

**&lt;**

**link**

rel

=

&quot;stylesheet&quot;

type

=

&quot;text/css&quot;

media

=

&quot;all&quot;

href

=

&quot;style-ielt9.css&quot;

**/&gt;**

&lt;!

&lbrack;

endif

&rbrack;

&minus;-

**&gt;**

> **Note :**
>
> Technically it&apos;s one more alternative: using &lbrack;**&lbrack;CSS
> hacks&rbrack;**&rbrack;(http://browserhacks.com/) to target IE&lt;9. It
> has the same impact as an IE&lt;9 only stylesheet, but you don&apos;t need a
> separate stylesheet for that. I do not recommend this option, though,
> as they produce invalid CSS code (which is but one of several reasons
> why the use of CSS hacks is generally frowned upon today).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch14">Chapter 14: Floats</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-1">Section 14.1: Float an Image Within Text</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The most basic use of a float is having text wrap around an image. The
> below code will produce two paragraphs and an image, with the second
> paragraph flowing around the image. Notice that it is always content
> *after* the floated element that flows around the floated element.
>
<h4>HTML:</h4>
>
> **&lt;p&gt;**Lorem ipsum dolor sit amet, consectetur adipiscing elit.
> Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed
> nisi. Nulla quis sem at nibh elementum imperdiet. Duis sagittis ipsum.
> Praesent mauris. Fusce nec tellus sed augue semper porta. Mauris
> massa. Vestibulum lacinia arcu eget nulla. **&lt;/p&gt; &lt;img**
> src=&quot;http://lorempixel.com/200/100/&quot; **/&gt;**

**&lt;p&gt;**Class aptent taciti sociosqu ad litora torquent per conubia
nostra, per inceptos himenaeos. Curabitur sodales ligula in libero. Sed
dignissim lacinia nunc. Curabitur tortor. Pellentesque nibh. Aenean
quam. In scelerisque sem at dolor. Maecenas mattis. Sed convallis
tristique sem. Proin ut ligula vel nunc egestas porttitor. Morbi lectus
risus, iaculis vel, suscipit quis, luctus non, massa. Fusce ac turpis
quis ligula lacinia aliquet. **&lt;/p&gt;** 

<h4>CSS:</h4>

```
img {
  **float**: left;
  **margin-right**: 1rem;
}
```

> This will be the output

[image036.jpg 7.48 x 7.05](./images/image036.jpg)

&lbrack;&lbrack;Codepen
Link&rbrack;&rbrack;(http://codepen.io/vishak-kavalur/pen/pbxvLx)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-2">Section 14.2: clear property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

The clear property is directly related to floats. Property Values:

none - Default. Allows floating elements on both sides

left - No floating elements allowed on the left side

right - No floating elements allowed on the right side

both - No floating elements allowed on either the left or the right side

initial - Sets this property to its default value. Read about initial

inherit - Inherits this property from its parent element. Read about inherit

```
**&lt;**
```

<h4>HTML</h4>

```
**&gt;**
**&lt;**
**head**
**&gt;**
**&lt;**
**style**
**&gt;**
img {
float: left;
}
p.clear {
clear: both;
}
**&lt;**
**/style**
**&gt;**
**&lt;**
**/head**
**&gt;**
**&lt;**
**body**
**&gt;**
**&lt;**
**img**
src
=
&quot;https://static.pexels.com/photos/69372/pexels-photo-69372-medium.jpeg&quot;
width
=
&quot;100&quot;
**&gt;**
**&lt;**
**p**
**&gt;**
Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem
ipsoum Lorem ipsoum Lorem
ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum
**&lt;**
**/p**
**&gt;**
**&lt;**
**p**
class
=
&quot;clear&quot;
**&gt;**
Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem
ipsoum
Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem ipsoum Lorem
ipsoum
**&lt;**
**/p**
**&gt;**
**&lt;**
**/body**
**&gt;**
**&lt;**
**/html**
**&gt;**
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-3">Section 14.3: Clearfix</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

The clearfix hack is a popular way to contain floats (N. Gallagher aka
&commat;necolas)

> Not to be confused with the clear property, clearfix is a *concept*
> (that is also related to floats, thus the possible confusion). To
> *contain floats*, you&apos;ve to add .cf or .clearfix class on the
> container (**the parent**) and style this class with a few rules
> described below.
>
> 3 versions with slightly different effects (sources :&lbrack;&lbrack;A new micro
> clearfix
> hack&rbrack;&rbrack;(http://nicolasgallagher.com/micro-clearfix-hack/)
> by N. Gallagher and &lbrack;&lbrack;clearfix
> reloaded&rbrack;&rbrack;(http://yuiblog.com/blog/2010/09/27/clearfix-reloaded-overflowhidden-demystified/)
> by T. J. Koblentz):
>
> **Clearfix (with top margin collapsing of contained floats still
> occurring)**

.cf

:

after

{

**content**

:

&quot;&quot;

;

**display**

:

table

;

}

.cf

:

after

{

**clear**

:

both

;

}

> **Clearfix also preventing top margin collapsing of contained floats**

*/&ast;&ast;*

*&ast; For modern browsers*

*&ast; 1. The space content is one way to avoid an Opera bug when the*

*&ast; contenteditable attribute is included anywhere else in the
document.*

*&ast; Otherwise it causes space to appear at the top and bottom of
elements*

*&ast; that are clearfixed.*

*&ast; 2. The use of &apos;table&apos; rather than &apos;block&apos; is only necessary if
using*

*&ast; &apos;:before&apos; to contain the top-margins of child elements.*

*&ast;/*

.cf

:

before

,

.cf

:

after

{

**content**

:

&quot; &quot;

;

*/&ast; 1 &ast;/*

**display**

:

table

;

*/&ast; 2 &ast;/*

}

.cf

:

after

{

**clear**

:

both

;

}

> **Clearfix with support of outdated browsers IE6 and IE7**

.cf

:

before

,

.cf

:

after

{

**content**

:

&quot; &quot;

;

**display**

:

table

;

}

.cf

:

after

{

**clear**

:

both

;

}

*/&ast;&ast;*

*&ast; For IE 6/7 only*

*&ast; Include this rule to trigger hasLayout and contain floats.*

*&ast;/*

.cf

{

&ast;

zoom

:

1

;

}

&lbrack;&lbrack;Codepen showing clearfix
effect&rbrack;&rbrack;(http://codepen.io/PhilippeVay/pen/OXEqgW?editors=0100)

> Other resource: &lbrack;&lbrack;Everything you know about clearfix is
> wrong&rbrack;&rbrack;(http://www.cssmojo.com/clearfix_block-formatting-context_and_hasLayout/)
> (clearfix and BFC - Block Formatting Context while hasLayout relates
> to outdated browsers IE6 maybe 7)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 14.4: In-line DIV using float
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The div is a block-level element, i.e it occupies the whole of the
> page width and the siblings are place one below the other irrespective
> of their width.

**&lt;**

**div**

**&gt;**

**&lt;**

**p**

**&gt;**

This is DIV 1

**&lt;**

**/p**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

**&gt;**

**&lt;**

**p**

**&gt;**

This is DIV 2

**&lt;**

**/p**

**&gt;**

**&lt;**

**/div**

**&gt;**

> The output of the following code will be

[image037.jpg 7.48 x 3.61](./images/image037.jpg)

> We can make them in-line by adding a float css property to the div.
>
> HTML:

**&lt;**

**div**

class

=

&quot;outer-div&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;inner-div1&quot;

**&gt;**

**&lt;**

**p**

**&gt;**

This is DIV 1

**&lt;**

**/p**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&quot;inner-div2&quot;

**&gt;**

**&lt;**

**p**

**&gt;**

This is DIV 2

**&lt;**

**/p**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> CSS

.inner-div1

{

**width**

:

50

&percnt;

;

**margin-right**

:

0

px

;

**float**

:

left

;

**background**

:

#337ab7

;

**padding**

:

50

px

0

px

;

}

.inner-div2

{

**width**

:

50

&percnt;

;

**margin-right**

:

0

px

;

**float**

:

left

;

**background**

:

#dd2c00

;

**padding**

:

50

px

0

px

;

}

p

{

**text-align**

:

center

;

}

[image038.jpg 7.48 x .97](./images/image038.jpg)

<a href="http://codepen.io/vishak-kavalur/pen/bZxbBy">Codepen</a>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-5">Section 14.5: Use of overflow property to clear floats</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Setting overflow value to hidden,auto or scroll to an element, will
> clear all the floats within that element.

  **overflow**:scroll

**Note:** using will always show the scrollbox

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-6">Section 14.6: Simple Two Fixed-Width Column Layout</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> A simple two-column layout consists of two fixed-width, floated
> elements. Note that the sidebar and content area are not the same
> height in this example. This is one of the tricky parts with
> multi-column layouts using floats, and requires workarounds to make
> multiple columns appear to be the same height.
>
<h4>HTML:</h4>

```
**&lt;**
**div**
class
=
&quot;wrapper&quot;
**&gt;**
**&lt;**
**div**
class
=
&quot;sidebar&quot;
**&gt;**
**&lt;**
**h**
**2**
**&gt;**
Sidebar
**&lt;**
**/h**
**2**
**&gt;**
**&lt;**
**p**
**&gt;**
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec
odio.
**&lt;**
**/p**
**&gt;**
**&lt;**
**/div**
**&gt;**
**&lt;**
**div**
class
=
&quot;content&quot;
**&gt;**
**&lt;**
**h**
**1**
**&gt;**
Content
**&lt;**
**/h**
**1**
**&gt;**
**&lt;**
**p**
**&gt;**
Class aptent taciti sociosqu ad litora torquent per conubia nostra, per
inceptos himenaeos.

Curabitur sodales ligula in libero. Sed dignissim lacinia nunc.
Curabitur tortor. Pellentesque

nibh. Aenean quam. In scelerisque sem at dolor. Maecenas mattis. Sed
convallis tristique sem. Proin

ut ligula vel nunc egestas porttitor. Morbi lectus risus, iaculis vel,
suscipit quis, luctus non,

massa. Fusce ac turpis quis ligula lacinia aliquet.

**&lt;**
**/p**
**&gt;**
**&lt;**
**/div**
**&gt;**
**&lt;**
**/div**
**&gt;**
```

<h4>CSS:</h4>

```
.wrapper
{
**width**
:
600
px
;
**padding**
:
20
px
;
**background-color**
:
pink
;
*/&ast; Floated elements don&apos;t use any height. Adding &quot;overflow:hidden;&quot;
forces the*

*parent element to expand to contain its floated children. &ast;/*

**overflow**
:
hidden
;
}
.sidebar
{
**width**
:
150
px
;
**float**
:
left
;
**background-color**
:
blue
;
}
.content
{
**width**
:
450
px
;
**float**
:
right
;
**background-color**
:
yellow
;
}
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch14-7">Section 14.7: Simple Three Fixed-Width Column Layout</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>HTML:</h4>

```
**&lt;**
**div**
class
=
&quot;wrapper&quot;
**&gt;**
**&lt;**
**div**
class
=
&quot;left-sidebar&quot;
**&gt;**
**&lt;**
**h**
**1**
**&gt;**
Left Sidebar
**&lt;**
**/h**
**1**
**&gt;**
**&lt;**
**p**
**&gt;**
Lorem ipsum dolor sit amet, consectetur adipiscing elit.
**&lt;**
**/p**
**&gt;**
**&lt;**
**/div**
**&gt;**
**&lt;**
**div**
class
=
&quot;content&quot;
**&gt;**
**&lt;**
**h**
**1**
**&gt;**
Content
**&lt;**
**/h**
**1**
**&gt;**
**&lt;**
**p**
**&gt;**
```

Class aptent taciti sociosqu ad litora torquent per conubia nostra, per
inceptos himenaeos.

Curabitur sodales ligula in libero. Sed dignissim lacinia nunc.
Curabitur tortor. Pellentesque

nibh. Aenean quam. In scelerisque sem at dolor. Maecenas mattis. Sed
convallis tristique sem. Proin

ut ligula vel nunc egestas porttitor. Morbi lectus risus, iaculis vel,
suscipit quis, luctus non,

massa.

**&lt;**

**/p**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&quot;right-sidebar&quot;

**&gt;**

**&lt;**

**h**

**1**

**&gt;**

Right Sidebar

**&lt;**

**/h**

**1**

**&gt;**

**&lt;**

**p**

**&gt;**

Fusce ac turpis quis ligula lacinia aliquet.

**&lt;**

**/p**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> CSS:

.wrapper

{

**width**

:

600

px

;

**background-color**

:

pink

;

**padding**

:

20

px

;

*/&ast; Floated elements don&apos;t use any height. Adding &quot;overflow:hidden;&quot;
forces the*

*parent element to expand to contain its floated children. &ast;/*

**overflow**

:

hidden

;

}

.left-sidebar

{

**width**

:

150

px

;

**background-color**

:

blue

;

**float**

:

left

;

}

.content

{

**width**

:

300

px

;

**background-color**

:

yellow

;

**float**

:

left

;

}

.right-sidebar

{

**width**

:

150

px

;

**background-color**

:

green

;

**float**

:

right

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 14.8: Two-Column Lazy/Greedy Layout
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> This layout uses one floated column to create a two-column layout with
> no defined widths. In this example the left sidebar is &quot;lazy,&quot; in
> that it only takes up as much space as it needs. Another way to say
> this is that the left sidebar is &quot;shrink-wrapped.&quot; The right content
> column is &quot;greedy,&quot; in that it takes up all the remaining space.
>
> HTML:
>
> **&lt;div** class=&quot;sidebar&quot;**&gt;**
>
> **&lt;h1&gt;**Sidebar**&lt;/h1&gt;**
>
> **&lt;img** src=&quot;http://lorempixel.com/150/200/&quot; **/&gt;**
>
> **&lt;/div&gt;**
>
> **&lt;div** class=&quot;content&quot;**&gt;**

**&lt;h1&gt;**Content**&lt;/h1&gt; &lt;p&gt;**Lorem ipsum dolor sit amet,
consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed
cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum
imperdiet. Duis sagittis ipsum. Praesent mauris. Fusce nec tellus sed
augue semper porta. Mauris massa. Vestibulum lacinia arcu eget nulla.
**&lt;/p&gt; &lt;p&gt;**Class aptent taciti sociosqu ad litora torquent per
conubia nostra, per inceptos himenaeos. Curabitur sodales ligula in
libero. Sed dignissim lacinia nunc. Curabitur tortor. Pellentesque nibh.
Aenean quam. In scelerisque sem at dolor. Maecenas mattis. Sed convallis
tristique sem. Proin ut ligula vel nunc egestas porttitor. Morbi lectus
risus, iaculis vel, suscipit quis, luctus non, massa. Fusce ac turpis
quis ligula lacinia aliquet. Mauris ipsum. Nulla metus metus,
ullamcorper vel, tincidunt sed, euismod in, nibh. **&lt;/p&gt; &lt;/div&gt;**
CSS:

.sidebar

{

*/&ast; &apos;display:table;&apos; shrink-wraps the column &ast;/*

**display**

:

table

;

**float**

:

left

;

**background-color**

:

blue

;

}

.content

{

*/&ast; &apos;overflow:hidden;&apos; prevents &apos;.content&apos; from flowing under
&apos;.sidebar&apos; &ast;/*

**overflow**

:

hidden

;

**background-color**

:

yellow

;

}

&lbrack;&lbrack;Fiddle&rbrack;&rbrack;(https://jsfiddle.net/ooprqsL0/)

# Chapter 15: Typography

**Parameter Details**

  *font-style*     italics or oblique
  *font-variant*   normal or small-caps

  *font-weight*    normal, bold or numeric from 100 to 900.

  *font-size*      The font size given in %, px, em, or any other valid CSS
                   measurement

  *line-height*    The line height given in %, px, em, or any other valid CSS
                   measurement

  *font-family*    This is for defining the family&apos;s name.
  hsl         (   240         ,   100%                ,   50%

*color* Any valid CSS color representation, like red, #00FF00, ) etc.

  *font-stretch*   Whether or not to use a confenced or expanded face from font.
                   Valid values are normal, ultracondensed, extra-condensed,
                   condensed, semi-condensed, semi-expanded, expanded,
                   extraexpanded or ultra-expanded
  *text-align*     start, end, left, right, center, justify, match-parent


> *text-decoration* none, underline, overline, line-through, initial,
> inherit;

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.1: The Font Shorthand
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> With the syntax:

element

{

**font**

:

&lbrack;

font-style

&rbrack;

&lbrack;

font-variant

&rbrack;

&lbrack;

font-weight

&rbrack;

&lbrack;

font-size/line-height

&rbrack;

&lbrack;

font-family

&rbrack;

;

}

> You can have all your font-related styles in one declaration with the
> font shorthand. Simply use the font property, and put your values in
> the correct order.
>
> For example, to make all p elements bold with a font size of 20px and
> using Arial as the font family typically you would code it as follows:

p

{

**font-weight**

:

bold

;

**font-size**

:

20

px

;

**font-family**

:

Arial

,

sans-serif

;

}

> However with the font shorthand it can be condensed as follows:

p

{

**font**

:

bold

20

px

Arial

,

sans-serif

;

}

> **Note**: that since font-style, font-variant, font-weight and
> line-height are optional, the three of them are skipped in this
> example. It is important to note that using the shortcut **resets**
> the other attributes not given. Another important point is that the
> two necessary attributes for the font shortcut to work are font-size
> and fontfamily. If they are not both included the shortcut is ignored.
>
> Initial value for each of the properties:

  **font-style**                          :   normal

  **font-variant**                           :   normal
  **font-weight**                           :   normal

> ;
>
> ;
>
> ;
>
> ;

  **font-stretch**                           :   normal


  **font-size**                         :    medium

  **line-height**                           :   normal

> ;
>
> ;
>
> font-family -- depends on user agent

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.2: Quotes
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

  **&lt;q**

> The quotes property is used to customize the opening and closing
> quotation marks of the **&gt;** tag.

q

{

**quotes**

:

&quot;

«

&quot;

&quot;

»

&quot;

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.3: Font Size
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> **HTML:**

**&lt;**

**div**

id

=

&quot;element-one&quot;

**&gt;**

Hello I am some text.

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

id

=

&quot;element-two&quot;

**&gt;**

Hello I am some smaller text.

**&lt;**

**/div**

**&gt;**

> **CSS:**

#element-one

{

**font-size**

:

30

px

;

}

#element-two

{

**font-size**

:

10

px

;

}

> The text inside #element-one will be 30px in size, while the text in
> #element-two will be 10px in size.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.4: Text Direction
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

div

{

**direction**

:

ltr

;

*/&ast; Default, text read read from left-to-right &ast;/*

}

.ex

{

**direction**

:

rtl

;

*/&ast; text read from right-to-left &ast;/*

}

.horizontal-tb

{

**writing-mode**

:

horizontal-tb

;

*/&ast; Default, text read from left-to-right and top-to-bottom. &ast;/*

}

.vertical-rtl

{

**writing-mode**

:

vertical-rl

;

*/&ast; text read from right-to-left and top-to-bottom &ast;/*

}

.vertical-ltr

{

**writing-mode**

:

vertical-rl

;

*/&ast; text read from left-to-right and top to bottom &ast;/*

}

> The direction property is used to change the horizontal text direction
> of an element.

  **direction**   :   ltr &vertbar; rtl &vertbar; initial &vertbar; inherit


> Syntax: ;
>
> The writing-mode property changes the alignment of text so it can be
> read from top-to-bottom or from left-to-right, depending on the
> language.

  **direction**   :   horizontal-tb &vertbar; vertical-rl &vertbar; vertical-lr

Syntax: ;

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.5: Font Stacks
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

**font-family**

:

&apos;Segoe UI&apos;

,

Tahoma

,

sans-serif

;

> The browser will attempt to apply the font face &quot;Segoe UI&quot; to the
> characters within the elements targeted by the above property. If this
> font is not available, or the font does not contain a glyph for the
> required character, the browser will fall back to Tahoma, and, if
> necessary, any sans-serif font on the user&apos;s computer. Note that any
> font names with more than one word such as &quot;Segoe UI&quot; need to have
> single or double quotes around them.

**font-family**

:

Consolas

,

&apos;Courier New&apos;

,

monospace

;

> The browser will attempt to apply the font face &quot;Consolas&quot; to the
> characters within the elements targeted by the above property. If this
> font is not available, or the font does not contain a glyph for the
> required character, the browser will fall back to &quot;Courier New,&quot;
> and, if necessary, any monospace font on the user&apos;s computer.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.6: Text Overflow
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The text-overflow property deals with how overflowed content should be
> signaled to users. In this example, the ellipsis represents clipped
> text.

.text

{

**overflow**

:

hidden

;

**text-overflow**

:

ellipsis

;

}

  **text-overflow**                        :   ellipsis

> Unfortunately, only works on a single line of text. There is no way to
> support ellipsis on the last line in standard CSS, but it can be
> achieved with non-standard webkit-only implementation of flexboxes.

.giveMeEllipsis

{

**overflow**

:

hidden

;

**text-overflow**

:

ellipsis

;

**display**

:

-webkit-box

;

-webkit-box-orient

:

vertical

;

-webkit-line-clamp

:

N

;

*/&ast; number of lines to show &ast;/*

**line-height**

:

X

;

*/&ast; fallback &ast;/*

**max-height**

:

X

&ast;

N

;

*/&ast; fallback &ast;/*

}

> Example (open in Chrome or Safari):

&lbrack;&lbrack;http://jsfiddle.net/csYjC/1131/&rbrack;&rbrack;(http://jsfiddle.net/csYjC/1131/)

> Resources:

&lbrack;&lbrack;https://www.w3.org/TR/2012/WD-css3-ui-20120117/#text-overflow0&rbrack;&rbrack;(https://www.w3.org/TR/2012/WD-css3-ui-20120117/#text-overflow0)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.7: Text Shadow
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> To add shadows to text, use the text-shadow property. The syntax is as
> follows:

**text-shadow**

:

horizontal-offset vertical-offset blur color

;

> **Shadow without blur radius**

h1

{

**text-shadow**

:

2

px

2

px

#0000FF

;

}

> This creates a blue shadow effect around a heading
>
> **Shadow with blur radius**
>
> To add a blur effect, add an option blur radius argument

h1

{

**text-shadow**

:

2

px

2

px

10

px

#0000FF

;

}

> **Multiple Shadows**
>
> To give an element multiple shadows, separate them with commas

h1

{

**text-shadow**

:

0

0

3

px

#FF0000

,

0

0

5

px

#0000FF

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.8: Text Transform
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The text-transform property allows you to change the capitalization of
> text. Valid values are: uppercase, capitalize, lowercase, initial,
> inherit, and none
>
> <h4>CSS</h4>

.example1

{

**text-transform**

:

uppercase

;

}

.example2

{

**text-transform**

:

capitalize

;

}

.example3
{
**text-transform**
:
lowercase
;
}
</code></pre>

> <h4>HTML</h4>

<pre><code>
**&lt;**
**p**
class
=
&quot;example1&quot;
**&gt;**
all letters in uppercase
*&lt;!&minus;-*
*&quot;ALL LETTERS IN UPPERCASE&quot;*
*&minus;-&gt;*
**&lt;**
**/p**
**&gt;**
**&lt;**
**p**
class
=
&quot;example2&quot;
**&gt;**
all letters in capitalize
*&lt;!&minus;-*
*&quot;All Letters In Capitalize (Sentence Case)&quot;*
*&minus;-&gt;*
**&lt;**
**/p**
**&gt;**
**&lt;**
**p**
class
=
&quot;example3&quot;
**&gt;**
all letters in lowercase
*&lt;!&minus;-*
*&quot;all letters in lowercase&quot;*
*&minus;-&gt;*
**&lt;**
**/p**
**&gt;**
</code></pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.9: Letter Spacing
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<pre><code>
h2
{
</code></pre>

*/&ast; adds a 1px space horizontally between each letter;*

*also known as tracking &ast;/*

**letter-spacing**

<pre><code>
:
1
px
;
}
</code></pre>

> The letter-spacing property is used to specify the space between the
> characters in a text.
>
> ! letter-spacing also supports negative values:

<pre><code>
p
{
**letter-spacing**
:
-1
px
;
}
</code></pre>

Resources:
&lbrack;&lbrack;https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.10: Text Indent
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<pre><code>
p
{
**text-indent**
:
50
px
;
}
</code></pre>

> The text-indent property specifies how much horizontal space text
> should be moved before the beginning of the first line of the text
> content of an element.
>
> Resources:
>
> &lbrack;&lbrack;Indenting only the first line of text in a
> paragraph?&rbrack;&rbrack;(http://stackoverflow.com/questions/5856952/indenting-only-the-first-line-of-text-in-a-paragraph)

&lbrack;&lbrack;https://www.w3.org/TR/CSS21/text.html#propdef-text-indent&rbrack;&rbrack;(https://www.w3.org/TR/CSS21/text.html#propdef-text-indent)
&lbrack;&lbrack;https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.11: Text Decoration
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The text-decoration property is used to set or remove decorations from
> text.

<pre><code>
h1
{
**text-decoration**
:
none
;
}
h2
{
**text-decoration**
:
overline
;
}
h3
{
**text-decoration**
:
line-through
;
}
h4
{
**text-decoration**
:
underline
;
}
</code></pre>

> text-decoration can be used in combination with text-decoration-style
> and text-decoration-color as a shorthand property:

<pre><code>
.title
{
**text-decoration**
:
underline
dotted
blue
;
}
</code></pre>

> This is a shorthand version of

<pre><code>
.title
{
**text-decoration-style**
:
dotted
;
**text-decoration-line**
:
underline
;
**text-decoration-color**
:
blue
;
}
</code></pre>

> It should be noted that the following properties are only supported in
> Firefox
>
> text-decoration-color text-decoration-line text-decoration-style
> text-decoration-skip

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.12: Word Spacing
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The word-spacing property specifies the spacing behavior between tags
> and words.
>
> **Possible values**
>
> a positive or negative *length* (using em px vh cm etc.) or
> *percentage* (using %) the keyword normal uses the font&apos;s default
> word spacing the keyword inherit takes the value from the parent
> element
>
> <h4>CSS</h4>

<pre><code>
.normal
{
**word-spacing**
:
normal
;
}
.narrow
{
**word-spacing**
:
-3
px
;
}
.extensive
{
**word-spacing**
:
10
px
;
}
</code></pre>

> <h4>HTML</h4>
>
> **&lt;p&gt;**
>
> **&lt;span** class=&quot;normal&quot;**&gt;**This is an example, showing the
> effect of &quot;word-spacing&quot;.**&lt;/span&gt;&lt;br&gt;**
>
> **&lt;span** class=&quot;narrow&quot;**&gt;**This is an example, showing the
> effect of &quot;word-spacing&quot;.**&lt;/span&gt;&lt;br&gt;** **&lt;span**
> class=&quot;extensive&quot;**&gt;**This is an example, showing the effect of
> &quot;word-spacing&quot;.**&lt;/span&gt;&lt;br&gt;**
>
> **&lt;/p&gt;**
>
> **Online-Demo**

&lbrack;&lbrack;Try it yourself&rbrack;&rbrack;(https://jsfiddle.net/91742Lxt/)

> **Further reading:**

&lbrack;&lbrack;word-spacing&rbrack; &lbrack;--&rbrack;
&lbrack;MDN&rbrack;&rbrack;(https://developer.mozilla.org/de/docs/Web/CSS/word-spacing)
&lbrack;&lbrack;word-spacing&rbrack; &lbrack;--&rbrack;
&lbrack;w3.org&rbrack;&rbrack;(https://www.w3.org/wiki/CSS/Properties/word-spacing)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 15.13: Font Variant
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Attributes:

***normal***

> Default attribute of fonts. ***small-caps***
>
> Sets every letter to uppercase, **but** makes the lowercase
> letters(from original text) smaller in size than the letters that
> originally uppercase.
>
> **CSS:**

<pre><code>
.smallcaps
{
**font-variant**
:
small-caps
;
}
</code></pre>

> **HTML:**

<pre><code>
**&lt;**
**p**
class
=
&quot;smallcaps&quot;
**&gt;**
Documentation about CSS Fonts
**&lt;**
**br**
**&gt;**
aNd ExAmpLe
**&lt;**
**/p**
**&gt;**
</code></pre>

> **Output:**

[image039.jpg 2.34 x .375](./images/image039.jpg)

> Note: The font-variant property is a shorthand for the properties:
> font-variant-caps, font-variant-numeric, fontvariant-alternates,
> font-variant-ligatures, and font-variant-east-asian.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
# Chapter 16: Flexible Box Layout (Flexbox)
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The Flexible Box module, or just &apos;flexbox&apos; for short, is a box model
> designed for user interfaces, and it allows users to align and
> distribute space among items in a container such that elements behave
> predictably when the page layout must accommodate different, unknown
> screen sizes. A flex container expands items to fill available space
> and shrinks them to prevent overflow.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 16.1: Dynamic Vertical and Horizontal Centering (alignitems, justify-content)
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> **Simple Example (centering a single element)**
>
> <h4>HTML</h4>

<pre><code>
**&lt;**
**div**
class
=
&quot;aligner&quot;
**&gt;**
**&lt;**
**div**
class
=
&quot;aligner-item&quot;
**&gt;**
...
**&lt;**
**/div**
**&gt;**
**&lt;**
**/div**
**&gt;**
</code></pre>

> <h4>CSS</h4>

<pre><code>
.aligner
{
**display**
:
flex
;
**align-items**
:
center
;
**justify-content**
:
center
;
}
.aligner-item
{
**max-width**
:
50
&percnt;
;
*/&ast;for demo. Use actual width instead.&ast;/*
}
</code></pre>

> Here is a
> &lbrack;&lbrack;demo&rbrack;&rbrack;(http://codepen.io/asim-coder/pen/ZOobqz).
>
> **Reasoning**

**Property Value Description**

> This centers the elements along the axis other than the one specified
> by flex-direction,
>
> align-items center i.e., vertical centering for a horizontal flexbox
> and horizontal centering for a vertical flexbox.
>
> This centers the elements along the axis specified by flex-direction.
> I.e., for a

<pre><code>
  **flex-direction**                                   :   row
  **flex-direction**                            :   column
</code></pre>

> justify-contentcenter horizontal () flexbox, this centers
> horizontally, and for a vertical flexbox () flexbox, this centers
> vertically)
>
> **Individual Property Examples**
>
> All of the below styles are applied onto this simple layout:

<pre><code>
**&lt;**
**div**
id
=
&quot;container&quot;
**&gt;**
**&lt;**
**div**
**&gt;**
**&lt;**
**/div**
**&gt;**
**&lt;**
**div**
**&gt;**
**&lt;**
**/div**
**&gt;**
**&lt;**
**div**
**&gt;**
**&lt;**
**/div**
**&gt;**
**&lt;**
**/div**
**&gt;**

where #container is the flex-box
.  **justify-content**                            **:**   **center**
</code></pre>


> **Example: on a horizontal flexbox**
>
> **CSS:**

<pre><code>
div
#container
{
**display**
:
flex
;
**flex-direction**
:
row
;
**justify-content**
:
center
;
}
</code></pre>

> **Outcome:**

[image040.jpg ](./images/image040.jpg)

Here is the <a href="https://jsfiddle.net/d6pc5bmd/">demo jsFiddle</a>.

  **justify-content**                            **:**   **center**

> **Example: on a vertical flexbox**
>
> **CSS:**

<pre><code>
div
#container
{
**display**
:
flex
;
**flex-direction**
:
column
;
**justify-content**
:
center
;
}
</code></pre>

> **Outcome:**

[image041.jpg](./images/image041.jpg)

Here is a <a href="https://jsfiddle.net/d6pc5bmd/1/">demo jsFiddle</a>.

  **align-content**                           **:**   **center**

> **Example: on a horizontal flexbox**
>
> **CSS:**

<pre><code>
div
#container
{
**display**
:
flex
;
**flex-direction**
:
row
;
**align-items**
:
center
;
}
</code></pre>

> **Outcome:**

[image042.jpg](./images/image042.jpg)

Here is the <a href="https://jsfiddle.net/d6pc5bmd/2/">demo jsFiddle</a>.

  **align-content**                           **:**   **center**

> **Example: on a vertical flexbox**
>
> **CSS:**

<pre><code>
div
#container
{
**display**
:
flex
;
**flex-direction**
:
column
;
**align-items**
:
center
;
}
</code></pre>

> **Outcome:**

[image043.jpg 6.97 x 6.15](./images/image043.jpg)

> Here is a &lbrack;&lbrack;demo&rbrack;&rbrack;(https://jsfiddle.net/d6pc5bmd/3/).
>
> **Example: Combination for centering both on horizontal flexbox**

```
div
#container
{
**display**
:
flex
;
**flex-direction**
:
row
;
**justify-content**
:
center
;
**align-items**
:
center
;
}
```

> **Outcome:**

[image044.jpog 6.93 x 6.13](./images/image044.jpg)

> Here is a &lbrack;&lbrack;demo&rbrack;&rbrack;(https://jsfiddle.net/d6pc5bmd/4/).
>
> **Example: Combination for centering both on vertical flexbox**

```
div
#container
{
**display**
:
flex
;
**flex-direction**
:
column
;
**justify-content**
:
center
;
**align-items**
:
center
;
}
```

> **Outcome:**

[image045.jpg 6.93 x 6.11](./images/image045.jpg)

Here is a <a href="https://jsfiddle.net/d6pc5bmd/5/">demo</a>.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 16.2: Sticky Variable-Height Footer
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
> This code creates a sticky footer. When the content doesn&apos;t reach the
> end of the viewport, the footer sticks to the bottom of the viewport.
> When the content extends past the bottom of the viewport, the footer
> is also pushed out of the viewport. &lbrack;*&lbrack;View
> Result&rbrack;*&rbrack;(https://jsfiddle.net/0t1f84tL/)
>
> **HTML:**

```
**&lt;**
**div**
class
=
&quot;header&quot;
**&gt;**
**&lt;**
**h**
**2**
**&gt;**
Header
**&lt;**
**/h**
**2**
**&gt;**
**&lt;**
**/div**
**&gt;**
**&lt;**
**div**
class
=
&quot;content&quot;
**&gt;**
**&lt;**
**h**
**1**
**&gt;**
Content
**&lt;**
**/h**
**1**
**&gt;**
**&lt;**
**p**
**&gt;**
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec
odio. Praesent libero.
Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum
imperdiet. Duis sagittis
ipsum. Praesent mauris. Fusce nec tellus sed augue semper porta. Mauris
massa. Vestibulum lacinia
arcu eget nulla. Class aptent taciti sociosqu ad litora torquent per
conubia nostra, per inceptos
himenaeos. Curabitur sodales ligula in libero.
**&lt;**
**/p**
**&gt;**
**&lt;**
**/div**
**&gt;**
**&lt;**
**div**
class
=
&quot;footer&quot;
**&gt;**
**&lt;**
**h**
**4**
**&gt;**
Footer
**&lt;**
**/h**
**4**
**&gt;**
**&lt;**
**/div**
**&gt;**
```

> **CSS:**

```
html, body {
  <b>height</b>: 100&percnt;;
}
body {
  <b>display</b>: flex;
  <b>flex-direction</b>: column;
}
.content {
/* Include &apos;0 auto&apos; for best browser compatibility. */
  <b>flex</b>: 10 auto;
}
.header, .footer {
  <b>background-color</b>: grey;
  <b>color</b>: white;
  <b>flex</b>: none;
}
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch16-3">Section 16.3: Optimally fit elements to their container</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<p>One of the nicest features of flexbox is to allow optimally fitting
containers to their parent element.</p>

&lbrack;&lbrack;Live demo&rbrack;&rbrack;(https://jsfiddle.net/6gfogoqk/).

> HTML:

```
&lt;div class = &quot;flex-container&quot;&gt;
&lt;div class = &quot;flex-item&quot;&gt;1 &lt;/div&gt;
&lt;div class = &quot;flex-item&quot;&gt;2 &lt;/div&gt;
&lt;div class = &quot;flex-item&quot;&gt;3 &lt;/div&gt;
&lt;div class = &quot;flex-item&quot;&gt;4 &lt;/div&gt;
&lt;div class = &quot;flex-item&quot;&gt;5 &lt;/div&gt;
&lt;/div
&gt;
```

> CSS:

```
.flex-container
{
<b>background-color</b>:#000;
<b>height</b>:100&percnt;; display: flex; flex-direction: row;
<b>flex-wrap</b>: wrap; justify-content: flex-start; align-content: stretch;
<b>align-items</b>: stretch;
}
.flex-item {
  <b>background-color</b>: #ccf;
  <b>margin</b>:0.1em; <b>flex-grow</b>: 1;
  <b>flex-shrink</b>:0;
  <b>flex-basis</b>:200px;
/* or % could be used to ensure a specific layout */
}
```

> **Outcome:**
>
> Columns adapt as screen is resized.

!&lbrack;&rbrack;(./images/image046.png){width="7.48037510936133in"
height="3.182736220472441in"}

<h3 id="ch16-4">Section 16.4: Holy Grail Layout using Flexbox</h3>

> &lbrack;&lbrack;Holy Grail
> layout&rbrack;&rbrack;(http://alistapart.com/article/holygrail) is a
> layout with a fixed height header and footer, and a center with 3
> columns. The 3 columns include a fixed width sidenav, a fluid center,
> and a column for other content like ads (the fluid center appears
> first in the markup). CSS Flexbox can be used to achieve this with a
> very simple markup:
>

<h4>HTML Markup:</h4>

```
**&lt;**
**div**
class
=
&quot;container&quot;
**&gt;**
**&lt;**
**header**
class
=
&quot;header&quot;
**&gt;**
Header
**&lt;**
**/header**
**&gt;**
**&lt;**
**div**
class
=
&quot;content-body&quot;
**&gt;**
**&lt;**
**main**
class
=
&quot;content&quot;
**&gt;**
Content
**&lt;**
**/main**
**&gt;**
**&lt;**
**nav**
class
=
&quot;sidenav&quot;
**&gt;**
Nav
**&lt;**
**/nav**
**&gt;**
**&lt;**
**aside**
class
=
&quot;ads&quot;
**&gt;**
Ads
**&lt;**
**/aside**
**&gt;**
**&lt;**
**/div**
**&gt;**
*&lt;**
**footer**
class
=
&quot;footer&quot;
**&gt;**
Footer
**&lt;**
**/footer**
**&gt;**
**&lt;**
**/div**
**&gt;**
```

> CSS:

```
body
{
**margin**
:
0
;
**padding**
:
0
;
}
.container
{
**display**
:
flex
;
**flex-direction**
:
column
;
**height**
:
100
vh
;
}
.header
{
**flex**
:
0
0
50
px
;
}
.content-body
{
**flex**
:
1
1
auto
;
**display**
:
flex
;
**flex-direction**
:
row
;
}
.content-body
.content
{
**flex**
:
1
1
auto
;
**overflow**
:
auto
;
}
.content-body
.sidenav
{
**order**
:
&minus;
1
;
**flex**
:
0
0
100
px
;
**overflow**
:
auto
;
}
.content-body
.ads
{
**flex**
:
0
0
100
px
;
**overflow**
:
auto
;
}
.footer
{
**flex**
:
0
0
50
px
;
}
```

<a href="https://jsfiddle.net/adityarb88/hek6ms0x/">jsFiddle Demo</a>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch16-5">Section 16.5: Perfectly aligned buttons inside cards with flexbox</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> It&apos;s a regular pattern in design these days to vertically align
> **call to actions** inside its containing cards like this:

!&lbrack;&rbrack;(./images/image047.jpg){width="7.48037510936133in"
height="3.3848195538057744in"}

> This can be achieved using a special trick with flexbox
>
> HTML
>
> **&lt;div** class=&quot;cards&quot;**&gt;**
>
> **&lt;div** class=&quot;card&quot;**&gt;** **&lt;p&gt;**Lorem ipsum Magna proident ex
> anim dolor ullamco pariatur reprehenderit culpa esse enim mollit
> labore dolore voluptate ullamco et ut sed qui minim.**&lt;/p&gt;**
> **&lt;p&gt;&lt;button&gt;**Action**&lt;/button&gt;&lt;/p&gt;**
>
> **&lt;/div&gt;**
>
> **&lt;div** class=&quot;card&quot;**&gt;** **&lt;p&gt;**Lorem ipsum Magna proident ex
> anim dolor ullamco pariatur reprehenderit culpa esse enim mollit
> labore dolore voluptate ullamco et ut sed qui minim.**&lt;/p&gt;**
> **&lt;p&gt;**Lorem ipsum Magna proident ex anim dolor ullamco pariatur
> reprehenderit culpa esse enim mollit labore dolore voluptate ullamco
> et ut sed qui minim.**&lt;/p&gt;** **&lt;p&gt;**Lorem ipsum Magna proident ex
> anim dolor ullamco pariatur reprehenderit culpa esse enim mollit
> labore dolore voluptate ullamco et ut sed qui minim.**&lt;/p&gt;**
> **&lt;p&gt;**Lorem ipsum Magna proident ex anim dolor ullamco pariatur
> reprehenderit culpa esse enim mollit labore dolore voluptate ullamco
> et ut sed qui minim.**&lt;/p&gt;**
> **&lt;p&gt;&lt;button&gt;**Action**&lt;/button&gt;&lt;/p&gt;**
>
> **&lt;/div&gt;**
>
> **&lt;/div&gt;**

  **display**                            :     flex


> First of all, we use CSS to apply ; to the container. This will create
> 2 columns equal in height with the content flowing naturally inside it
>
> CSS

```
.cards
{
**display**
:
flex
;
}
.card
{
**border**
:
1
px
solid
#ccc
;
**margin**
:
10
px
10
px
;
**padding**
:
0
20
px
;
}
button
{
**height**
:
40
px
;
**background**
:
#fff
;
**padding**
:
0
40
px
;
**border**
:
1
px
solid
#000
;
}
p
:
last-child
{
**text-align**
:
center
;
}
```

> The layout will change and become like this:

!&lbrack;&rbrack;(./images/image048.jpg){width="7.48037510936133in"
height="3.0046391076115486in"}

  **display**                            :     flex


> In order to move the buttons to the bottom of the block, we need to
> apply ; to the card itself with the direction set to column. After
> that, we should select the last element inside the card and set the
> margin-top to auto. This will push the last paragraph to the bottom of
> the card and achieve the required result.
>

<h4>Final CSS:</h4>

```
.cards
{
**display**
:
flex
;
}
.card
{
**border**
:
1
px
solid
#ccc
;
**margin**
:
10
px
10
px
;
**padding**
:
0
20
px
;
**display**
:
flex
;
**flex-direction**
:
column
;
}
button
{
**height**
:
40
px
;
**background**
:
#fff
;
**padding**
:
0
40
px
;
**border**
:
1
px
solid
#000
;
}
p
:
last-child
{
**text-align**
:
center
;
**margin-top**
:
auto
;
}
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch16-6">Section 16.6: Same height on nested containers</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> This code makes sure that all nested containers are always the same
> height. This is done by assuring that all nested elements are the same
> height as the containing parent div. &lbrack;&lbrack;See working
> example&rbrack;&rbrack;(https://jsfiddle.net/3wwh7ewp/):
> &lbrack;&lbrack;https://jsfiddle.net/3wwh7ewp/&rbrack;&rbrack;(https://jsfiddle.net/3wwh7ewp/)
> This effect is achieved due to the property align-items being set to
> stretch by default.
>

<h4>HTML</h4>

```
**&lt;**
**div**
class
=
&quot;container&quot;
**&gt;**
**&lt;**
**div**
style
=
&quot;background-color: red&quot;
**&gt;**
Some
**&lt;**
**br**
**/&gt;**
data
**&lt;**
**br**
**/&gt;**
to make
**&lt;**
**br**
**/&gt;**
a height
**&lt;**
**br**
**/&gt;**
**&lt;**
**/div**
**&gt;**
**&lt;**
**div**
style
=
&quot;background-color: blue&quot;
**&gt;**
Fewer
**&lt;**
**br**
**/&gt;**
lines
**&lt;**
**br**
**/&gt;**
**&lt;**
**/div**
**&gt;**
**&lt;**
**/div**
**&gt;**
```

<h4>CSS</h4>

```
.container
{
**display**
:
flex
;
**align-items**
:
stretch
;
// Default
value
}
```

Note: &lbrack;&lbrack;Does not work on IE versions under 10&rbrack;&rbrack;(http://caniuse.com/#search=flexbox)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="ch17">Chapter 17: Cascading and Specificity</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch17-1">Section 17.1: Calculating Selector Specificity</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Each individual CSS Selector has its own specificity value. Every
> selector in a sequence increases the sequence&apos;s overall specificity.
> Selectors fall into one of three different specificity groups: *A*,
> *B* and *c*. When multiple selector sequences select a given element,
> the browser uses the styles applied by the sequence with the highest
> overall specificity.

**Group Comprised of Examples**

A.  id selectors #foo class selectors .bar

  title
  hover
  colspan                                       =      &quot;2&quot;
  nth-child

B.  attribute selectors &lbrack;&rbrack;, &lbrack;&rbrack; pseudo-classes :, :(2)

type selectors div, li

  ::before                 ,   ::first-letter


> *c* pseudo-elements
>
> Group *A* is the most specific, followed by Group *B*, then finally
> Group *c*.
>
> The universal selector (&ast;) and combinators (like &gt; and &#126;) have no
> specificity.
>
> **Example 1: Specificity of various selector sequences**

#foo

#baz

{

}

*/&ast; a=2, b=0, c=0 &ast;/*

#foo

.bar

{

}

*/&ast; a=1, b=1, c=0 &ast;/*

#foo

{

}

*/&ast; a=1, b=0, c=0 &ast;/*

.bar

:

hover

{

}

*/&ast; a=0, b=2, c=0 &ast;/*

div

.bar

{

}

*/&ast; a=0, b=1, c=1 &ast;/*

:

hover

{

}

*/&ast; a=0, b=1, c=0 &ast;/*

&lbrack;

title

&rbrack;

{

}

*/&ast; a=0, b=1, c=0 &ast;/*

.bar

{

}

*/&ast; a=0, b=1, c=0 &ast;/*

div ul

&plus;

li

{

}

*/&ast; a=0, b=0, c=3 &ast;/*

p

::

after

{

}

*/&ast; a=0, b=0, c=2 &ast;/*

&ast;::

before

{

}

*/&ast; a=0, b=0, c=1 &ast;/*

::

before

{

}

*/&ast; a=0, b=0, c=1 &ast;/*

div

{

}

*/&ast; a=0, b=0, c=1 &ast;/*

&ast;

{

}

*/&ast; a=0, b=0, c=0 &ast;/*

> **Example 2: How specificity is used by the browser**
>
> Imagine the following CSS implementation:

#foo

{

**color**

:

blue

;

}

.bar

{

**color**

:

red

;

**background**

:

black

;

}

> Here we have an ID selector which declares color as *blue*, and a
> class selector which declares color as *red* and background as
> *black*.
>
> An element with an ID of #foo and a class of .bar will be selected by
> both declarations. ID selectors have a Group *A* specificity and class
> selectors have a Group *B* specificity. An ID selector outweighs any
> number of class selectors.

  **color**   :   blue   ; from the #foo selector and the      **background**   :   black

> Because of this, ; from the .bar selector will be
>
> applied to the element. The higher specificity of the ID selector will
> cause the browser to ignore the .bar selector&apos;s color declaration.
>
> Now imagine a different CSS implementation:

.bar

{

**color**

:

red

;

**background**

:

black

;

}

.baz

{

**background**

:

white

;

}

> Here we have two class selectors; one of which declares color as *red*
> and background as *black*, and the other declares background as
> *white*.
>
> An element with both the .bar and .baz classes will be affected by
> both of these declarations, however the problem we have now is that
> both .bar and .baz have an identical Group *B* specificity. The
> cascading nature of CSS resolves this for us: as .baz is defined
> *after* .bar, our element ends up with the *red* color from .bar but
> the *white* background from .baz.
>
> **Example 3: How to manipulate specificity**
>
> The last snippet from Example 2 above can be manipulated to ensure our
> .bar class selector&apos;s color declaration is used instead of that of
> the .baz class selector.

.bar

{

}

*/&ast; a=0, b=1, c=0 &ast;/*

.baz

{

}

*/&ast; a=0, b=1, c=0 &ast;/*

> The most common way to achieve this would be to find out what other
> selectors can be applied to the .bar selector sequence. For example,
> if the .bar class was only ever applied to span elements, we could
> modify the .bar selector to span.bar. This would give it a new Group
> *C* specificity, which would override the .baz selector&apos;s lack
> thereof:

span

.bar

{

}

*/&ast; a=0, b=1, c=1 &ast;/*

.baz

{

}

*/&ast; a=0, b=1, c=0 &ast;/*

  .bar.bar


> However it may not always possible to find another common selector
> which is shared between any element which uses the .bar class. Because
> of this, CSS allows us to duplicate selectors to increase specificity.
> Instead of just .bar, we can use instead (See &lbrack;&lbrack;The grammar of
> Selectors, W3C
> Recommendation&rbrack;&rbrack;(https://www.w3.org/TR/css3-selectors/#grammar)).
> This still selects any element with a class of .bar, but now has
> double the Group *B* specificity:

.bar

.bar

{

}

*/&ast; a=0, b=2, c=0 &ast;/*

.baz

{

}

*/&ast; a=0, b=1, c=0 &ast;/*

> **!important and inline style declarations**
>
> The !important flag on a style declaration and styles declared by the
> HTML style attribute are considered to have a greater specificity than
> any selector. If these exist, the style declaration they affect will
> overrule other declarations regardless of their specificity. That is,
> unless you have more than one declaration that contains an !important
> flag for the same property that apply to the same element. Then,
> normal specificity rules will apply to those properties in reference
> to each other.
>
> Because they completely override specificity, the use of !important is
> frowned upon in most use cases. One should use it as little as
> possible. To keep CSS code efficient and maintainable in the long run,
> it&apos;s almost always better to increase the specificity of the
> surrounding selector than to use !important.
>
> One of those rare exceptions where !important is not frowned upon, is
> when implementing generic helper classes like a .hidden or
> .background-yellow class that are supposed to always override one or
> more properties wherever they are encountered. And even then, you need
> to know what you&apos;re doing. The last thing you want, when writing
> maintainable CSS, is to have !important flags throughout your CSS.
>
> **A final note**

  b                    =5,                            c


> A common misconception about CSS specificity is that the Group *A*,
> *B* and *c* values should be combined with each other (a=1,=1 =&gt;
> 151). This is **not** the case. If this were the case, having 20 of a
> Group *B* or *c* selector would be enough to override a single Group
> *A* or *B* selector respectively. The three groups should be regarded
> as individual levels of specificity. Specificity cannot be represented
> by a single value.
>
> When creating your CSS style sheet, you should maintain the lowest
> specificity as possible. If you need to make the specificity a little
> higher to overwrite another method, make it higher but as low as
> possible to make it higher. You shouldn&apos;t need to have a selector
> like this:

body

.page

header

.container

nav div

#main-nav

li a

{

}

> This makes future changes harder and pollutes that css page.
>
> You can calculate the specificity of your selector
> &lbrack;&lbrack;here&rbrack;&rbrack;(http://specificity.keegan.st/)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="ch17-2">Section 17.2: The !important declaration</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The !important declaration is used to override the usual specificity
> in a style sheet by giving a higher priority to a

  property                :   value !important
 
 
> rule. Its usage is: ;

#mydiv

{

**font-weight**

:

bold

!important

;

*/&ast; This property won&apos;t be overridden*

*by the rule below &ast;/*

}

#outerdiv

#mydiv

{

**font-weight**

:

normal

;

*/&ast; #mydiv font-weight won&apos;t be set to normal*

*even if it has a higher specificity because*

*of the !important declaration above &ast;/*

}

> Avoiding the usage of !important is strongly recommended (unless
> absolutely necessary), because it will disturb the natural flow of css
> rules which can bring uncertainty in your style sheet. Also it is
> important to note that when multiple !important declarations are
> applied to the same rule on a certain element, the one with the higher
> specificity will be the ona applied.
>
> Here are some examples where using !important declaration can be
> justified:
>
> If your rules shouldn&apos;t be overridden by any inline style of the
> element which is written inside style attribute of the html element.
>
> To give the user more control over the web accessibility, like
> increasing or decreasing size of the font-size, by overriding the
> author style using !important.
>
> For testing and debugging using inspect element.
>
> See also:

&lbrack;**&lbrack;W3C - 6 Assigning property values, Cascading, and Inheritance &minus;-
6.4.2 !important
rules&rbrack;**&rbrack;(https://www.w3.org/TR/CSS22/cascade.html#important-rules)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 17.3: Cascading
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Cascading and specificity are used together to determine the final
> value of a CSS styling property. They also define the mechanisms for
> resolving conflicts in CSS rule sets.
>
> **CSS Loading order**
>
> Styles are read from the following sources, in this order:

1.  User Agent stylesheet (The styles supplied by the browser vendor)

2.  User stylesheet (The additional styling a user has set on his/her
    browser)

3.  Author stylesheet (Author here means the creator of the
    webpage/website)

  **&lt;style**
 
 
> Maybe one or more .css files
>
> In the **&gt;** element of the HTML document

4.  Inline styles (In the style attribute on an HTML element)

> The browser will lookup the corresponding style(s) when rendering an
> element.
>
> **How are conflicts resolved?**
>
> When only one CSS rule set is trying to set a style for an element,
> then there is no conflict, and that rule set is used.
>
> When multiple rule sets are found with conflicting settings, first the
> Specificty rules, and then the Cascading rules are used to determine
> what style to use.
>
> **Example 1 - Specificity rules**

.mystyle

{

**color**

:

blue

;

}

*/&ast; specificity: 0, 0, 1, 0 &ast;/*

div

{

**color**

:

red

;

}

*/&ast; specificity: 0, 0, 0, 1 &ast;/*

**&lt;**

**div**

class

=

&quot;mystyle&quot;

**&gt;**

Hello World

**&lt;**

**/div**

**&gt;**

> What color will the text be? (hover to see the answer)

blue

> First the specificity rules are applied, and the one with the highest
> specificity &quot;wins&quot;.
>
> **Example 2 - Cascade rules with identical selectors**
>
> *External css file*

.class

{

**background**

:

#FFF

;

}

> *Internal css (in HTML file)*

**&lt;**

**style**

**&gt;**

.class {

background: #000;

}

**&lt;**

**style**

**&gt;**

> In this case, where you have identical selectors, the cascade kicks
> in, and determines that the last one loaded &quot;wins&quot;.

**Example 3 - Cascade rules after Specificity rules**

body

&gt;

.mystyle

{

**background-color**

:

blue

;

}

*/&ast; specificity: 0, 0, 1, 1 &ast;/*

.otherstyle

&gt;

div

{

**background-color**

:

red

;

}

*/&ast; specificity: 0, 0, 1, 1 &ast;/*

**&lt;**

**body**

class

=

&quot;otherstyle&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;mystyle&quot;

**&gt;**

Hello World

**&lt;**

**/div**

**&gt;**

**&lt;**

**/body**

**&gt;**

What color will the background be?

red

  .otherstyle                                        &gt;   div
 
 
> After applying the specificity rules, there&apos;s still a conflict
> between blue and red, so the cascading rules are applied on top of the
> specificity rules. Cascading looks at the load order of the rules,
> whether inside the same .css file or in the collection of style
> sources. The last one loaded overrides any earlier ones. In this case,
> the rule &quot;wins&quot;.
>
> **A final note**
>
> Selector specificity always take precedence.
>
> Stylesheet order break ties.
>
> Inline styles trump everything.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 17.4: More complex specificity example
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

div

{

**font-size**

:

7

px

;

**border**

:

3

px

dotted

pink

;

**background-color**

:

yellow

;

**color**

:

purple

;

}

body

.mystyle

&gt;

div

.myotherstyle

{

**font-size**

:

11

px

;

**background-color**

:

green

;

}

#elmnt1

{

**font-size**

:

24

px

;

**border-color**

:

red

;

}

.mystyle

.myotherstyle

{

**font-size**

:

16

px

;

**background-color**

:

black

;

**color**

:

red

;

}

**&lt;**

**body**

class

=

&quot;mystyle&quot;

**&gt;**

**&lt;**

**div**

id

=

&quot;elmnt1&quot;

class

=

&quot;myotherstyle&quot;

**&gt;**

Hello, world!

**&lt;**

**/div**

**&gt;**

**&lt;**

**/body**

**&gt;**

> What borders, colors, and font-sizes will the text be? font-size:

  ------------------------------------------------------------------------------------------
  **font-size**   :   24   ;, since #elmnt1 rule set has the highest specificity **&lt;div**
                           for the                                               
  --------------- --- ---- ----------------------------------------------------- -----------

  ------------------------------------------------------------------------------------------

> **&gt;** in question, every property here is set.
>
> border:
>
> ;. The border-color red is taken from #elmnt1 rule set, since it has
> the highest

  ------------------------------------------------------------------------
  **border**          :   3px dotted red
  ------------------- --- ------------------------------------------------

  ------------------------------------------------------------------------

> specificity. The other properties of the border, border-thickness, and
> border-style are from the div rule set.
>
> background-color:

  ------------------------------------------------------------------------------------------------------
  **background-color**   :   green   ;. The background-color is   body.mystyle   &gt;   div.myotherstyle
                                     set in the div,                                  
  ---------------------- --- ------- ---------------------------- -------------- ---- ------------------

  ------------------------------------------------------------------------------------------------------

  -----------------------------------------------------------------------
  .mystyle .myotherstyle
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> , and rule sets. The specificities are (0, 0, 1) vs. (0, 2, 2) vs. (0,
> 2, 0), so the middle one &quot;wins&quot;.
>
> color:

  **color**   :   red   ;. The color is set in both the div .mystyle .myotherstyle
                        and                                 

> rule sets. The latter has the higher specificity of (0, 2, 0) and
> &quot;wins&quot;.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
# Chapter 18: Colors
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 18.1: currentColor
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> currentColor returns the computed color value of the current element.
>
> **Use in same element**
>
> Here currentColor evaluates to red since the color property is set to
> red:

div

{

**color**

:

red

;

**border**

:

5

px

solid

currentColor

;

**box-shadow**

:

0

0

5

px

currentColor

;

}

> In this case, specifying currentColor for the border is most likely
> redundant because omitting it should produce identical results. Only
> use currentColor inside the border property within the same element if
> it would be overwritten otherwise due to a more specific selector.
>
> Since it&apos;s the computed color, the border will be green in the
> following example due to the second rule overriding the first:

div

{

**color**

:

blue

;

**border**

:

3

px

solid

currentColor

;

**color**

:

green

;

}

> **Inherited from parent element**
>
> The parent&apos;s color is inherited, here currentColor evaluates to
> &apos;blue&apos;, making the child element&apos;s border-color blue.

.parent-class

{

**color**

:

blue

;

}

.parent-class

.child-class

{

**border-color**

:

currentColor

;

}

> currentColor can also be used by other rules which normally would not
> inherit from the color property, such as background-color. The example
> below shows the children using the color set in the parent as its
> background:

.parent-class

{

**color**

:

blue

;

}

.parent-class

.child-class

{

**background-color**

:

currentColor

;

}

> **Possible Result:**

[image049.png 5.2 x 3.09](./images/image049.png)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 18.2: Color Keywords
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Most browsers support using color keywords to specify a color. For
> example, to set the color of an element to blue, use the blue keyword:

```
.some-class {
  **color**: blue;
}
```

> CSS keywords are not case sensitive---blue, Blue and BLUE will all
> result in #0000FF.
>
> **Color Keywords**

**Color name Hex value RGB values Color**

AliceBlue #F0F8FF rgb(240,248,255)

AntiqueWhite #FAEBD7 rgb(250,235,215)

Aqua #00FFFF rgb(0,255,255)

Aquamarine #7FFFD4 rgb(127,255,212)

Azure #F0FFFF rgb(240,255,255)

Beige #F5F5DC rgb(245,245,220)

Bisque #FFE4C4 rgb(255,228,196)

Black #000000 rgb(0,0,0)

BlanchedAlmond #FFEBCD rgb(255,235,205)

Blue #0000FF rgb(0,0,255)

BlueViolet #8A2BE2 rgb(138,43,226)

Brown #A52A2A rgb(165,42,42)

|   ---                                                          |     |
|   BurlyWood                  #DEB887                           |     |
|                              rgb(222,184,135)                  |     |
|   ---                                                          |     |
|   CadetBlue                  #5F9EA0                           |     |
|                              rgb(95,158,160)                   |     |
|                                                                |     |
|   Chartreuse                 #7FFF00                           |     |
|                              rgb(127,255,0)                    |     |
|                                                                |     |
|   Chocolate                  #D2691E                           |     |
|                              rgb(210,105,30)                   |     |
|                                                                |     |
|   Coral                      #FF7F50                           |     |
|                              rgb(255,127,80)                   |     |
|                                                                |     |
|   CornflowerBlue             #6495ED                           |     |
|                              rgb(100,149,237)                  |     |
|                                                                |     |
|   Cornsilk                   #FFF8DC                           |     |
|                              rgb(255,248,220)                  |     |
|                                                                |     |
|   Crimson                    #DC143C                           |     |
|                              rgb(220,20,60)                    |     |
|                                                                |     |
|   Cyan                       #00FFFF                           |     |
|                              rgb(0,255,255)                    |     |
|                                                                |     |
|   DarkBlue                   #00008B                           |     |
|                              rgb(0,0,139)                      |     |
|                                                                |     |
|   DarkCyan                   #008B8B                           |     |
|                              rgb(0,139,139)                    |     |
|                                                                |     |
|   DarkGoldenRod              #B8860B                           |     |
|                              rgb(184,134,11)                   |     |
|                                                                |     |
|   DarkGray                   #A9A9A9                           |     |
|                              rgb(169,169,169)                  |     |
|                                                                |     |
|   DarkGrey                   #A9A9A9                           |     |
|                              rgb(169,169,169)                  |     |
|                                                                |     |
|   DarkGreen                  #006400                           |     |
|                              rgb(0,100,0)                      |     |
|                                                                |     |
|   DarkKhaki                  #BDB76B                           |     |
|                              rgb(189,183,107)                  |     |
|                                                                |     |
|   DarkMagenta                #8B008B            rgb(139,0,139) |     |
|                                                                |     |
|   DarkOliveGreen             #556B2F            rgb(85,107,47) |     |
|                                                                |     |
|   DarkOrange                 #FF8C00            rgb(255,140,0) |     |
|                                                                |     |
|                                                                |     |
|  DarkOrchid                 #9932CC            rgb(153,50,204) |     |
|                                                                |     |
|   DarkRed                    #8B0000            rgb(139,0,0)   |     |
|                                                                |     |
|                                                                |     |
| DarkSalmon                 #E9967A            rgb(233,150,122) |     |
|                                                                |     |
|                                                                |     |
| DarkSeaGreen               #8FBC8F            rgb(143,188,143) |     |
|                                                                |     |
|   DarkSlateBlue              #483D8B            rgb(72,61,139) |     |
|                                                                |     |
|   DarkSlateGray              #2F4F4F            rgb(47,79,79)  |     |
|                                                                |     |
|   DarkSlateGrey              #2F4F4F            rgb(47,79,79)  |     |
|                                                                |     |
|   DarkTurquoise              #00CED1            rgb(0,206,209) |     |
|                                                                |     |
|   DarkViolet                 #9400D3            rgb(148,0,211) |     |
|   ---                                                          |     |

|   DeepPink                   #FF1493 rgb(255,20,147)           |     |
|   DeepSkyBlue                #00BFFF rgb(0,191,255)            |     |
|                                                                |     |
|   DimGray                    #696969 rgb(105,105,105)          |     |
|                                                                |     |
|   DimGrey                    #696969 rgb(105,105,105)          |     |
|                                                                |     |
|   DodgerBlue                 #1E90FF rgb(30,144,255)           |     |
|                                                                |     |
|   FireBrick                  #B22222 rgb(178,34,34)            |     |
|                                                                |     |
|   FloralWhite                #FFFAF0 rgb(255,250,240)          |     |
|                                                                |     |
|   ForestGreen                #228B22 rgb(34,139,34)            |     |
|                                                                |     |
|   Fuchsia                    #FF00FF rgb(255,0,255)            |     |
|                                                                |     |
|   Gainsboro                  #DCDCDC rgb(220,220,220)          |     |
|                                                                |     |
|   GhostWhite                 #F8F8FF rgb(248,248,255)          |     |
|                                                                |     |
|   Gold                       #FFD700 rgb(255,215,0)            |     |
|                                                                |     |
|   GoldenRod                  #DAA520 rgb(218,165,32)           |     |
|                                                                |     |
|   Gray                       #808080 rgb(128,128,128)          |     |
|                                                                |     |
|   Grey                       #808080 rgb(128,128,128)          |     |
|                                                                |     |
|   Green                      #008000 rgb(0,128,0)              |     |
|                                                                |     |
|   GreenYellow                #ADFF2F rgb(173,255,47)           |     |
|                                                                |     |
|   HoneyDew                   #F0FFF0 rgb(240,255,240)          |     |
|                                                                |     |
|   HotPink                    #FF69B4 rgb(255,105,180)          |     |
|                                                                |     |
|   IndianRed                  #CD5C5C rgb(205,92,92)            |     |
|                                                                |     |
|   Indigo                     #4B0082 rgb(75,0,130)             |     |
|                                                                |     |
|   Ivory                      #FFFFF0 rgb(255,255,240)          |     |
|                                                                |     |
|   Khaki                      #F0E68C rgb(240,230,140)          |     |
|                                                                |     |
|   Lavender                   #E6E6FA rgb(230,230,250)          |     |
|                                                                |     |
|   LavenderBlush              #FFF0F5 rgb(255,240,245)          |     |
|                                                                |     |
|   LawnGreen                  #7CFC00 rgb(124,252,0)            |     |
|                                                                |     |
|   LemonChiffon               #FFFACD rgb(255,250,205)          |     |
|                                                                |     |
|   LightBlue                  #ADD8E6 rgb(173,216,230)          |     |
| | LightCoral #F08080       |                               |   |     |
| | rgb(240,128,128)         |                               |   |     |
| |                          |                               |   |     |
| | LightCyan #E0FFFF        |                               |   |     |
| | rgb(224,255,255)         |                               |   |     |
| |                          |                               |   |     |
| | LightGoldenRodYellow     |                               |   |     |
| | #FAFAD2 rgb(250,250,210) |                               |   |     |
| | LightGray                | #D3D3D3 rgb(211,211,211)      |   |     |
| | LightGrey                | #D3D3D3 rgb(211,211,211)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | LightGreen               | #90EE90 rgb(144,238,144)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | LightPink                | #FFB6C1 rgb(255,182,193)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | LightSalmon              | #FFA07A rgb(255,160,122)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | LightSeaGreen            | #20B2AA rgb(32,178,170)       |   |     |
| |--------------------------|-------------------------------|   |     |
| | LightSkyBlue             | #87CEFA rgb(135,206,250)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | LightSlateGray           | #778899 rgb(119,136,153)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | LightSlateGrey           | #778899 rgb(119,136,153)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | LightSteelBlue           | #B0C4DE rgb(176,196,222)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | LightYellow              | #FFFFE0 rgb(255,255,224)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | Lime                     | #00FF00 rgb(0,255,0)          |   |     |
| |--------------------------|-------------------------------|   |     |
| | LimeGreen                | #32CD32 rgb(50,205,50)        |   |     |
| |--------------------------|-------------------------------|   |     |
| | Linen                    | #FAF0E6 rgb(250,240,230)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | Magenta                  | #FF00FF rgb(255,0,255)        |   |     |
| |--------------------------|-------------------------------|   |     |
| | Maroon                   | #800000 rgb(128,0,0)          |   |     |
| |--------------------------|-------------------------------|   |     |
| | MediumAquaMarine         | #66CDAA rgb(102,205,170)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | MediumBlue               | #0000CD rgb(0,0,205)          |   |     |
| |--------------------------|-------------------------------|   |     |
| | MediumOrchid             | #BA55D3 rgb(186,85,211)       |   |     |
| |--------------------------|-------------------------------|   |     |
| | MediumPurple             | #9370DB rgb(147,112,219)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | MediumSeaGreen           | #3CB371 rgb(60,179,113)       |   |     |
| |--------------------------|-------------------------------|   |     |
| | MediumSlateBlue          | #7B68EE rgb(123,104,238)      |   |     |
| |--------------------------|-------------------------------|   |     |
| | MediumSpringGreen        | #00FA9A rgb(0,250,154)        |   |     |
| |--------------------------|-------------------------------|   |     |
| | MediumTurquoise          | #48D1CC rgb(72,209,204)       |   |     |
| |--------------------------|-------------------------------|   |     |
| | MediumVioletRed          | #C71585 rgb(199,21,133)       |   |     |
| -------------------------------------------------------------- |     |
|   MidnightBlue               #191970            rgb(25,25,112) |     |
|   ---                                                          |     |
| ----------------------- ------------------ ------------------- |     |
|                                                                |     |
| MintCream                  #F5FFFA            rgb(245,255,250) |     |
|                                                                |     |
|                                                                |     |
| MistyRose                  #FFE4E1            rgb(255,228,225) |     |
|                                                                |     |
|                                                                |     |
| Moccasin                   #FFE4B5            rgb(255,228,181) |     |
|                                                                |     |
|                                                                |     |
| NavajoWhite                #FFDEAD            rgb(255,222,173) |     |
|                                                                |     |
|   Navy                       #000080            rgb(0,0,128)   |     |
|                                                                |     |
|                                                                |     |
| OldLace                    #FDF5E6            rgb(253,245,230) |     |
|                                                                |     |
|   Olive                      #808000            rgb(128,128,0) |     |
|                                                                |     |
|                                                                |     |
|  OliveDrab                  #6B8E23            rgb(107,142,35) |     |
|                                                                |     |
|   Orange                     #FFA500            rgb(255,165,0) |     |
|                                                                |     |
|   OrangeRed                  #FF4500            rgb(255,69,0)  |     |
|                                                                |     |
|   Orchid                     #DA70D6                           |     |
|                              rgb(218,112,214)                  |     |
|                                                                |     |
|   PaleGoldenRod              #EEE8AA                           |     |
|                              rgb(238,232,170)                  |     |
|                                                                |     |
|   PaleGreen                  #98FB98                           |     |
|                              rgb(152,251,152)                  |     |
|                                                                |     |
|   PaleTurquoise              #AFEEEE                           |     |
|                              rgb(175,238,238)                  |     |
|                                                                |     |
|   PaleVioletRed              #DB7093                           |     |
|                              rgb(219,112,147)                  |     |
|                                                                |     |
|   PapayaWhip                 #FFEFD5                           |     |
|                              rgb(255,239,213)                  |     |
|                                                                |     |
|   PeachPuff                  #FFDAB9                           |     |
|                              rgb(255,218,185)                  |     |
|                                                                |     |
|   Peru                       #CD853F                           |     |
|                              rgb(205,133,63)                   |     |
|                                                                |     |
|   Pink                       #FFC0CB                           |     |
|                              rgb(255,192,203)                  |     |
|                                                                |     |
|   Plum                       #DDA0DD                           |     |
|                              rgb(221,160,221)                  |     |
|                                                                |     |
|   PowderBlue                 #B0E0E6                           |     |
|                              rgb(176,224,230)                  |     |
|                                                                |     |
|   Purple                     #800080                           |     |
|                              rgb(128,0,128)                    |     |
|                                                                |     |
|   RebeccaPurple              #663399                           |     |
|                              rgb(102,51,153)                   |     |
|                                                                |     |
|   Red                        #FF0000                           |     |
|                              rgb(255,0,0)                      |     |
|                                                                |     |
|   RosyBrown                  #BC8F8F                           |     |
|                              rgb(188,143,143)                  |     |
|                                                                |     |
|   RoyalBlue                  #4169E1                           |     |
|                              rgb(65,105,225)                   |     |
|                                                                |     |
|   SaddleBrown                #8B4513                           |     |
|                              rgb(139,69,19)                    |     |
|   ---                                                          |     |

Salmon #FA8072 rgb(250,128,114)

SandyBrown #F4A460 rgb(244,164,96)

SeaGreen #2E8B57 rgb(46,139,87)

SeaShell #FFF5EE rgb(255,245,238)

Sienna #A0522D rgb(160,82,45)

Silver #C0C0C0 rgb(192,192,192)

SkyBlue #87CEEB rgb(135,206,235)

SlateBlue #6A5ACD rgb(106,90,205)

SlateGray #708090 rgb(112,128,144)

SlateGrey #708090 rgb(112,128,144)

Snow #FFFAFA rgb(255,250,250)

SpringGreen #00FF7F rgb(0,255,127)

SteelBlue #4682B4 rgb(70,130,180)

Tan #D2B48C rgb(210,180,140)

Teal #008080 rgb(0,128,128)

Thistle #D8BFD8 rgb(216,191,216)

Tomato #FF6347 rgb(255,99,71)

Turquoise #40E0D0 rgb(64,224,208)

Violet #EE82EE rgb(238,130,238)

Wheat #F5DEB3 rgb(245,222,179)

White #FFFFFF rgb(255,255,255)

WhiteSmoke #F5F5F5 rgb(245,245,245)

Yellow #FFFF00 rgb(255,255,0)

YellowGreen #9ACD32 rgb(154,205,50)

> In addition to the named colors, there is also the keyword
> transparent, which represents a fully-transparent black:

  -----------------------------------------------------------------------
  rgba
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> (0,0,0,0)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 18.3: Hexadecimal Value
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> **Background**
>
> CSS colors may also be represented as a hex triplet, where the members
> represent the red, green and blue components of a color. Each of these
> values represents a number in the range of 00 to FF, or 0 to 255 in
> decimal notation. Uppercase and/or lowercase Hexadecimal values may be
> used (i.e. #3fc = #3FC = #33ffCC). The browser interprets #369 as
> #336699. If that is not what you intended but rather wanted #306090,
> you need to specify that explicitly.
>
> The total number of colors that can be represented with hex notation
> is 256 &Hat; 3 or 16,777,216.
>
> **Syntax**

**color**

:

#rrggbb

;

**color**

:

&num;

rgb

**Value Description**

rr 00 - FF for the amount of red

gg

00

&minus;

FF

for the amount of green

bb

00

&minus;

FF

for the amount of blue

.some-class

{

*/&ast; This is equivalent to using the color keyword &apos;blue&apos; &ast;/*

**color**

:

#0000FF

;

}

.also-blue

{

*/&ast; If you want to specify each range value with a single number, you
can!*

*This is equivalent to &apos;#0000FF&apos; (and &apos;blue&apos;) &ast;/*

**color**

:

#00F

;

}

> &lbrack;&lbrack;Hexadecimal
> notation&rbrack;&rbrack;(https://en.wikipedia.org/wiki/Hexadecimal) is
> used to specify color values in the RGB color format, per the &lbrack;&lbrack;W3C&apos;s
> &apos;Numerical color&rbrack;
> &lbrack;values&apos;&rbrack;&rbrack;(https://www.w3.org/TR/css3-color/#numerical).
>
> There are a lot of tools available on the Internet for looking up
> hexadecimal (or simply hex) color values.
>
> Search for &quot;**hex color palette**&quot; or &quot;**hex color picker**&quot; with
> your favorite web browser to find a bunch of options!
>
> Hex values always start with a pound sign (#), are up to six
> &quot;digits&quot; long, and are case-insensitive: that is, they don&apos;t care
> about capitalization. #FFC125 and #ffc125 are the same color.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 18.4: rgb() Notation
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> RGB is an additive color model which represents colors as mixtures of
> red, green, and blue light. In essence, the RGB representation is the
> decimal equivalent of the Hexadecimal Notation. In Hexadecimal each
> number ranges from 00-FF which is equivalent to 0-255 in decimal and
> 0%-100% in percentages.

.some-class

{

*/&ast; Scalar RGB, equivalent to &apos;blue&apos;&ast;/*

**color**

:

rgb

(

0

,

0

,

255

)

;

}

.also-blue

{

*/&ast; Percentile RGB values&ast;/*

**color**

:

rgb

(

0

&percnt;

,

0

&percnt;

,

100

&percnt;

)

;

}

> **Syntax**

rgb

(

&lt;

red

&gt;

,

&lt;green

&gt;

,

&lt;blue

&gt;

)

**Value Description**

  -----------------------------------------------------------------------
  **&lt;red**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> **&gt;** an integer from 0 - 255 or percentage from 0 - 100%

  -----------------------------------------------------------------------
  **&lt;green**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

  -----------------------------------------------------------------------
  **&lt;blue**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> **&gt;** an integer from 0 - 255 or percentage from 0 - 100% **&gt;** an
> integer from 0 - 255 or percentage from 0 - 100%

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 18.5: rgba() Notation
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Similar to rgb() notation, but with an additional alpha (opacity)
> value.

.red

{

*/&ast; Opaque red &ast;/*

**color**

:

rgba

(

255

,

0

,

0

,

1

)

;

}

.red-50p

{

*/&ast; Half-translucent red. &ast;/*

**color**

:

rgba

(

255

,

0

,

0

,

.5

)

;

}

> **Syntax**

rgba

(

&lt;

red

&gt;

,

&lt;green

&gt;

,

&lt;blue

&gt;

,

&lt;alpha

&gt;

)

;

**Value Description**

  -----------------------------------------------------------------------
  **&lt;red**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> **&gt;** an integer from 0 - 255 or percentage from 0 - 100%

  -----------------------------------------------------------------------
  **&lt;green**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> **&gt;** an integer from 0 - 255 or percentage from 0 - 100%

  -----------------------------------------------------------------------
  **&lt;blue**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> **&gt;** an integer from 0 - 255 or percentage from 0 - 100%

  -----------------------------------------------------------------------
  **&lt;alpha**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> **&gt;** a number from 0 - 1, where 0.0 is fully transparent and 1.0 is
> fully opaque

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 18.6: hsl() Notation
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> HSL stands for **hue** (&quot;which color&quot;), **saturation** (&quot;how much
> color&quot;) and **lightness** (&quot;how much white&quot;).
>
> Hue is represented as an angle from 0° to 360° (without units), while
> saturation and lightness are represented as percentages.

p

{

**color**

:

hsl

(

240

,

100

&percnt;

,

50

&percnt;

)

;

*/&ast; Blue &ast;/*

}

!&lbrack;&rbrack;(./images/image189.jpg){width="7.48037510936133in"
height="5.610277777777778in"}

> **Syntax**

**color**

:

hsl

(

&lt;

hue

&gt;

,

&lt;saturation

&gt;

&percnt;

,

&lt;lightness

&gt;

&percnt;

)

;

**Value Description**

  -----------------------------------------------------------------------
  **&lt;hue**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> specified in degrees around the color wheel (without units), where 0°
> is red, 60° is yellow, 120° is

  -----------------------------------------------------------------------
  **&lt;saturation**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> **&gt;** green, 180° is cyan, 240° is blue, 300° is magenta, and 360° is
> red specified in percentage where 0% is fully desaturated (grayscale)
> and 100% is fully saturated (vividly **&gt;** colored)

  -----------------------------------------------------------------------
  **&lt;lightness**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> **&gt;** specified in percentage where 0% is fully black and 100% is
> fully white
>
> **Notes**
>
> A saturation of 0% always produces a grayscale color; changing the hue
> has no effect.
>
> A lightness of 0% always produces black, and 100% always produces
> white; changing the hue or saturation has no effect.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 18.7: hsla() Notation
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Similar to hsl() notation, but with an added alpha (opacity) value.
>
> hsla(240, 100%, 50%, 0) */&ast; transparent &ast;/* hsla(240, 100%, 50%,
> 0.5) */&ast; half-translucent blue &ast;/* hsla(240, 100%, 50%, 1) */&ast;
> fully opaque blue &ast;/*
>
> **Syntax**

hsla

(

&lt;

hue

&gt;

,

&lt;saturation

&gt;

&percnt;

,

&lt;lightness

&gt;

&percnt;

,

&lt;alpha

&gt;

)

;

**Value Description**

  -----------------------------------------------------------------------
  **&lt;hue**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> specified in degrees around the color wheel (without units), where 0°
> is red, 60° is yellow, 120° is
>
> **&gt;** green, 180° is cyan, 240° is blue, 300° is magenta, and 360° is
> red

  -----------------------------------------------------------------------
  **&lt;saturation**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

  -----------------------------------------------------------------------
  **&lt;lightness**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> **&gt;** percentage where 0% is fully desaturated (grayscale) and 100%
> is fully saturated (vividly colored) **&gt;** percentage where 0% is
> fully black and 100% is fully white

  -----------------------------------------------------------------------
  **&lt;alpha**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

**&gt;** a number from 0 - 1 where 0 is fully transparent and 1 is fully
opaque

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
# Chapter 19: Opacity
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 19.1: Opacity Property
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> An element&apos;s opacity can be set using the opacity property. Values
> can be anywhere from 0.0 (transparent) to 1.0 (opaque).
>
> **Example Usage**

**&lt;**

**div**

style

=

&quot;opacity:0.8;&quot;

**&gt;**

This is a partially transparent element

**&lt;**

**/div**

**&gt;**

**Property Value Transparency**

  -----------------------------------------------------------------------
  **opacity**: 1.0;
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> Opaque

  -----------------------------------------------------------------------
  **opacity**: 0.75;
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> 25% transparent (75% Opaque)

  -----------------------------------------------------------------------
  **opacity**: 0.5;
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> 50% transparent (50% Opaque)

  -----------------------------------------------------------------------
  **opacity**: 0.25;
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

  -----------------------------------------------------------------------
  **opacity**: 0.0;
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> 75% transparent (25% Opaque) Transparent

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 19.2: IE Compatibility for &apos;opacity&apos;
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

To use

opacity

in all versions of IE, the order is:

.transparent-element

{

*/&ast; for IE 8 & 9 &ast;/*

-ms-filter

:

&quot;progid:DXImageTransform.Microsoft.Alpha(Opacity=60)&quot;

;

// IE8

*/&ast; works in IE 8 & 9 too, but also 5, 6, 7 &ast;/*

**filter**

:

alpha

(

opacity

=

60

)

;

// IE

5

&minus;

7

*/&ast; Modern Browsers &ast;/*

**opacity**

:

0.6

;

}

# Chapter 20: Length Units

**Unit Description**

> &percnt; Define sizes in terms of parent objects or current object dependent
> on property em Relative to the font-size of the element (2em means 2
> times the size of the current font) rem Relative to font-size of the
> root element vw Relative to 1% of the width of the viewport&ast; vh
> Relative to 1% of the height of the viewport&ast; vmin Relative to 1% of
> viewport&apos;s&ast; smaller dimension vmax Relative to 1% of viewport&apos;s&ast;
> larger dimension cm centimeters mm millimeters in inches (1in = 96px =
> 2.54cm) px pixels (1px = 1/96th of 1in) pt points (1pt = 1/72 of 1in)
> pc picas (1pc = 12 pt) s seconds (used for animations and transitions)
> ms milliseconds (used for animations and transitions) ex Relative to
> the x-height of the current font ch Based on the width of the zero (0)
> character fr fractional unit (used for CSS Grid Layout)
>
> A CSS distance measurement is a number immediately followed by a
> length unit (px, em, pc, in, ...)
>
> CSS supports a number of length measurements units. They are absolute
> or relative.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 20.1: Creating scalable elements using rems and ems
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

Version ≥ 3

> You can use rem defined by the font-size of your html tag to style
> elements by setting their font-size to a value of rem and use em
> inside the element to create elements that scale with your global
> font-size.
>
> **HTML:**

**&lt;**

**input**

type

=

&quot;button&quot;

value

=

&quot;Button&quot;

**&gt;**

**&lt;**

**input**

type

=

&quot;range&quot;

**&gt;**

**&lt;**

**input**

type

=

&quot;text&quot;

value

=

&quot;Text&quot;

**&gt;**

> **Relevant CSS:**

html

{

**font-size**

:

16

px

;

}

input

&lbrack;

type

=

&quot;button&quot;

&rbrack;

{

**font-size**

:

1

rem

;

**padding**

:

0.5

em

2

em

;

}

input

&lbrack;

type

=

&quot;range&quot;

&rbrack;

{

**font-size**

:

1

rem

;

**width**

:

10

em

;

}

input

&lbrack;

type

=

text

&rbrack;

{

**font-size**

:

1

rem

;

**padding**

:

0.5

em

;

}

> **Possible Result:**

!&lbrack;&rbrack;(./images/image190.jpg){width="6.34375in"
height="2.9583333333333335in"}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 20.2: Font size with rem
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> CSS3 introduces a few new units, including the
> &lbrack;&lbrack;rem&rbrack;&rbrack;(https://www.w3.org/TR/css-values/#font-relative-lengths)
> unit, which stands for &quot;root em&quot;. Let&apos;s look at how rem works.
>
> First, let&apos;s look at the differences between em and rem.

  -----------------------------------------------------------------------
  **&lt;html**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> **em**: Relative to the font size of the parent. This causes the
> compounding issue **rem**: Relative to the font size of the root or
> **&gt;** element. This means it&apos;s possible to declare a single font
> size for the html element and define all rem units to be a percentage
> of that.
>
> The main issue with using rem for font sizing is that the values are
> somewhat difficult to use. Here is an example of some common font
> sizes expressed in rem units, assuming that the base size is 16px :
>
> 10px = 0.625rem 12px = 0.75rem
>
> 14px = 0.875rem
>
> 16px = 1rem (base)
>
> 18px = 1.125rem
>
> 20px = 1.25rem
>
> 24px = 1.5rem
>
> 30px = 1.875rem
>
> 32px = 2rem
>
> **CODE:**

Version ≥ 3 html {

**font-size**

:

16

px

;

}

h1

{

**font-size**

:

2

rem

;

*/&ast; 32px &ast;/*

}

p

{

**font-size**

:

1

rem

;

*/&ast; 16px &ast;/*

}

li

{

**font-size**

:

1.5

em

;

*/&ast; 24px &ast;/*

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 20.3: vmin and vmax
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> **vmin**: Relative to 1 percent of the viewport&apos;s smaller dimension
> **vmax**: Relative to 1 percent of the viewport&apos;s larger dimension
>
> In other words, 1 vmin is equal to the smaller of *1 vh* and *1 vw*
>
> 1 vmax is equal to the larger of *1 vh* and *1 vw*

**Note**: vmax is &lbrack;&lbrack;not
supported&rbrack;&rbrack;(http://caniuse.com/#feat=viewport-units) in:

> any version of Internet Explorer Safari before version 6.1

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 20.4: vh and vw
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

CSS3 introduced two units for representing size.

vh

, which stands for

viewport height

is relative to 1% of the viewport height

vw

, which stands for

viewport width

is relative to 1% of the viewport width

Version

≥

3

div

{

**width**

:

20

vw

;

**height**

:

20

vh

;

}

> Above, the size for the div takes up 20% of the width and height of
> the viewport

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 20.5: using percent %
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> One of the useful unit when creating a responsive application.
>
> Its size depends on its parent container.
>
> **Equation:**

( Parent Container&apos;s width ) &ast; ( Percentage(%) ) = Output

> **For Example:**
>
> *Parent* has **100px** width while the *Child* has **50%**.
>
> **On the output**, the *Child*&apos;s width will be half(50%) of the
> *Parent*&apos;s, which is **50px**.
>
> <h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;parent&quot;

**&gt;**

PARENT

**&lt;**

**div**

class

=

&quot;child&quot;

**&gt;**

CHILD

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

**&lt;**

**style**

**&gt;**

&ast;

{

color: #CCC;

}

.parent

{

background-color: blue;

width: 100px;

}

.child

{

background-color: green;

width: 50%;

}

**&lt;**

**/style**

**&gt;**

> **OUTPUT**

!&lbrack;&rbrack;(./images/image191.jpg){width="1.40625in" height="0.875in"}

# Chapter 21: Pseudo-Elements

  -------------------------------------------------------------------------
  **pseudo-element**   **Description**
  -------------------- ----------------------------------------------------

  -------------------------------------------------------------------------

::after Insert content after the content of an element

::before Insert content before the content of an element

> ::first-letter Selects the first letter of each element

::first-line Selects the first line of each element

::selection Matches the portion of an element that is selected by a user

> Used to create a backdrop that hides the underlying document for an
> element in the top layer&apos;s ::backdrop stack

::placeholder Allows you to style the placeholder text of a form element
(Experimental)

::marker For applying list-style attributes on a given element
(Experimental)

  -----------------------------------------------------------------------
  ::spelling-error
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> Represents a text segment which the browser has flagged as incorrectly
> spelled (Experimental)

  -----------------------------------------------------------------------
  ::grammar-error
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> Represents a text segment which the browser has flagged as
> grammatically incorrect (Experimental)
>
> Pseudo-elements, just like pseudo-classes, are added to a CSS
> selectors but instead of describing a special state, they allow you to
> scope and style certain parts of an html element.
>
> For example, the ::first-letter pseudo-element targets only the first
> letter of a block element specified by the selector.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 21.1: Pseudo-Elements
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Pseudo-elements are added to selectors but instead of describing a
> special state, they allow you to style certain parts of a document.
>
> The content attribute is required for pseudo-elements to render;
> however, the attribute can have an empty value

  ------------------------------------------------------------------------
  **content**                                   :      &quot;&quot;
  --------------------------------------------- ------ -------------------

  ------------------------------------------------------------------------

> (e.g. ).

div

::

after

{

**content**

:

&apos;after&apos;

;

**color**

:

red

;

**border**

:

1

px

solid

red

;

}

div

{

**color**

:

black

;

**border**

:

px

1

solid

black

;

**padding**

:

1

px

;

}

div

::

before

{

**content**

:

&apos;before&apos;

;

**color**

:

green

;

**border**

:

1

px

solid

green

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 21.2: Pseudo-Elements in Lists
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Pseudo-elements are often used to change the look of lists (mostly for
> unordered lists, ul).
>
> The first step is to remove the default list bullets:

ul

{

**list-style-type**

:

none

;

}

> Then you add the custom styling. In this example, we will create
> gradient boxes for bullets.

li

:

before

{

**content**

:

&quot;&quot;

;

**display**

:

inline-block

;

**margin-right**

:

10

px

;

**height**

:

10

px

;

**width**

:

10

px

;

**background**

:

linear-gradient

(

red

,

blue

)

;

}

> <h4>HTML</h4>

**&lt;**

**ul**

**&gt;**

**&lt;**

**li**

**&gt;**

Test I

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

Test II

**&lt;**

**/li**

**&gt;**

**&lt;**

**/ul**

**&gt;**

> **Result**

!&lbrack;&rbrack;(./images/image193.jpg){width="2.4479166666666665in"
height="1.3125in"}

# Chapter 22: Positioning

**Parameter Details**

> Default value. Elements render in order, as they appear in the
> document flow. The top, right, bottom, static left and z-index
> properties do not apply.

  -----------------------------------------------------------------------
  **left**                        :       20px
  ------------------------------- ------- -------------------------------

  -----------------------------------------------------------------------

  -------------------------------------------------------------------------
  relative   LEFT position
  ---------- --------------------------------------------------------------
  fixed      The element is positioned relative to the browser window

  absolute   The element is positioned relative to its first positioned
             (not static) ancestor element

  initial    Sets this property to its default value.

  inherit    Inherits this property from its parent element.
  -------------------------------------------------------------------------

> The element is positioned relative to its normal position, so adds 20
> pixels to the element&apos;s

  ------------------------------------------------------------------------
  **position**                        :    static
  ----------------------------------- ---- -------------------------------

  ------------------------------------------------------------------------

> Experimental feature. It behaves like within its parent until a given
> offset threshold sticky

  -----------------------------------------------------------------------
  **position**                          :    fixed
  ------------------------------------- ---- ----------------------------

  -----------------------------------------------------------------------

> is reached, then it acts as .

unset Combination of initial and inherit. More info
&lbrack;&lbrack;here&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/unset).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 22.1: Overlapping Elements with z-index
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> To change the default &lbrack;&lbrack;stack
> order&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)
> positioned elements (position property set to relative, absolute or
> fixed), use the z-index property.
>
> The higher the z-index, the higher up in the stacking context (on the
> z-axis) it is placed.
>
> **Example**
>
> In the example below, a z-index value of 3 puts green on top, a
> z-index of 2 puts red just under it, and a z-index of 1 puts blue
> under that.
>
> <h4>HTML</h4>

**&lt;**

**div**

id

=

&quot;div1&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

id

=

&quot;div2&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

id

=

&quot;div3&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

div

{

**position**

:

absolute

;

**height**

:

200

px

;

**width**

:

200

px

;

}

div

#div1

{

**z-index**

:

1

;

**left**

:

0

px

;

**top**

:

0

px

;

**background-color**

:

blue

;

}

div

#div2

{

**z-index**

:

3

;

**left**

:

100

px

;

**top**

:

100

px

;

**background-color**

:

green

;

}

div

#div3

{

**z-index**

:

2

;

**left**

:

50

px

;

**top**

:

150

px

;

**background-color**

:

red

;

}

> This creates the following effect:

!&lbrack;&rbrack;(./images/image194.jpg){width="3.6458333333333335in"
height="3.8645833333333335in"}

> See a working example at
> &lbrack;&lbrack;JSFiddle&rbrack;&rbrack;(https://jsfiddle.net/esnc10tq/).
>
> **Syntax**

**z-index**

:

&lbrack;

number

&rbrack;

&vertbar;

auto

;

**Parameter Details**

> An integer value. A higher number is higher on the z-index stack. 0 is
> the default value. Negative
>
> number values are allowed.

auto Gives the element the same stacking context as its parent.
(**Default**)

> **Remarks**
>
> All elements are laid out in a 3D axis in CSS, including a depth axis,
> measured by the z-index property. z-index only works on positioned
> elements: (see: &lbrack;&lbrack;Why does z-index need a defined position to
> work?&rbrack;&rbrack;(https://www.sitepoint.com/community/t/why-does-z-index-need-a-defined-position-to-work/46115)).
> The only value where it is ignored is the default value, static.
>
> Read about the z-index property and Stacking Contexts in the &lbrack;&lbrack;CSS
> Specification&rbrack;&rbrack;(https://drafts.csswg.org/css-position/#layered-presentation)
> on layered presentation and at the &lbrack;&lbrack;Mozilla Developer
> Network&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/z-index).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 22.2: Absolute Position
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> When absolute positioning is used the box of the desired element is
> taken out of the *Normal Flow* and it no longer affects the position
> of the other elements on the page. Offset properties:

1.  top

2.  left

3.  right

4.  bottom

> specify the element should appear in relation to its next non-static
> containing element.

.abspos

{

**position**

:

absolute

;

**top**

:

0

px

;

**left**

:

500

px

;

}

  ------------------------------------------------------------------------
  class                     =     &quot;abspos&quot;
  ------------------------- ----- ----------------------------------------

  ------------------------------------------------------------------------

> This code will move the box containing element with attribute down 0px
> and right 500px relative to its containing element.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 22.3: Fixed position
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Defining position as fixed we can remove an element from the document
> flow and set its position relatively to the browser window. One
> obvious use is when we want something to be visible when we scroll to
> the bottom of a long page.

#stickyDiv

{

**position**

:

fixed

;

**top**

:

10

px

;

**left**

:

10

px

;

}

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 22.4: Relative Position
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Relative positioning moves the element in relation to where it would
> have been in *normal flow* .Offset properties:

1.  top

2.  left

3.  right

4.  bottom

> are used to indicate how far to move the element from where it would
> have been in normal flow.

.relpos

{

**position**

:

relative

;

**top**

:

20

px

;

**left**

:

30

px

;

}

> This code will move the box containing element with attribute
> class=&quot;relpos&quot; 20px down and 30px to the right from where it would
> have been in normal flow.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 22.5: Static positioning
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The default position of an element is static. To quote
> &lbrack;&lbrack;MDN&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/position#values):

This keyword lets the element use the normal behavior, that is it is
laid out in its current position in the

flow. The top, right, bottom, left and z-index properties do not apply.

.element

{

**position**

:

static

;

}

# Chapter 23: Layout Control

**Value Effect**

> none Hide the element and prevent it from occupying space.
>
> block Block element, occupy 100% of the available width, break after
> element.
>
> inline Inline element, occupy no width, no break after element.
>
> inline-block Taking special properties from both inline and block
> elements, no break, but can have width. inline-flex Displays an
> element as an inline-level flex container.
>
> inline-table The element is displayed as an inline-level table. grid
> Behaves like a block element and lays out its content according to the
> grid model.
>
> flex Behaves like a block element and lays out its content according
> to the flexbox model.
>
> inherit Inherit the value from the parent element.
>
> Reset the value to the default value taken from behaviors described in
> the HTML specifications or initial from the browser/user default
> stylesheet.
>
> table Behaves like the HTML table element.

  -----------------------------------------------------------------------
  **&lt;td**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> table-cell Let the element behave like a **&gt;** element

  -----------------------------------------------------------------------
  **&lt;col**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

  -----------------------------------------------------------------------
  **&lt;tr**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

  -----------------------------------------------------------------------
  **&lt;li**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> table-column Let the element behave like a **&gt;** element table-row
> Let the element behave like a **&gt;** element list-item Let the element
> behave like a **&gt;** element.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 23.1: The display property
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The display CSS property is fundamental for controlling the layout and
> flow of an HTML document. Most elements have a default display value
> of either block or inline (though some elements have other default
> values).
>
> **Inline**
>
> An inline element occupies only as much width as necessary. It stacks
> horizontally with other elements of the same type and may not contain
> other non-inline elements.

**&lt;**

**span**

**&gt;**

This is some

**&lt;**

**b**

**&gt;**

bolded

**&lt;**

**/b**

**&gt;**

text!

**&lt;**

**/span**

**&gt;**

  -----------------------------------------------------------------------
  **&lt;span**                   **&gt;** and                     **&lt;b**
  ---------------------------- ------------------------------ -----------

  -----------------------------------------------------------------------

> As demonstrated above, two inline elements, **&gt;**, are in-line (hence
> the name) and do not break the flow of the text.
>
> **Block**
>
> A block element occupies the maximum available width of its&apos; parent
> element. It starts with a new line and, in contrast to inline
> elements, it does not restrict the type of elements it may contain.

**&lt;**

**div**

**&gt;**

Hello world!

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

**&gt;**

This is an example!

**&lt;**

**/div**

**&gt;**

> The div element is block-level by default, and as shown above, the two
> block elements are vertically stacked and, unlike the inline elements,
> the flow of the text breaks.
>
> **Inline Block**
>
> The inline-block value gives us the best of both worlds: it blends the
> element in with the flow of the text while allowing us to use padding,
> margin, height and similar properties which have no visible effect on
> inline elements.
>
> Elements with this display value act as if they were regular text and
> as a result are affected by rules controlling the flow of text such as
> text-align. By default they are also shrunk to the the smallest size
> possible to accommodate their content.

*&lt;!&minus;-*

*Inline: unordered list*

*&minus;-&gt;*

**&lt;**

**style**

**&gt;**

li {

display : inline;

background : lightblue;

padding:10px;

border-width:2px;

border-color:black;

border-style:solid;

}

**&lt;**

**/style**

**&gt;**

**&lt;**

**ul**

**&gt;**

**&lt;**

**li**

**&gt;**

First Element

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

Second Element

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

Third Element

**&lt;**

**/li**

**&gt;**

**&lt;**

**/ul**

**&gt;**

&lt;!&minus;-

block: unordered list

&minus;-

**&gt;**

**&lt;**

**style**

**&gt;**

li

{

display : block;

background : lightblue;

padding:10px;

border-width:2px;

border-color:black;

border-style:solid;

}

**&lt;**

**/style**

**&gt;**

**ul**

**&lt;**

**&gt;**

**&lt;**

**li**

**&gt;**

First Element

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

Second Element

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

Third Element

**&lt;**

**/li**

**&gt;**

**&lt;**

**/ul**

**&gt;**

&lt;!&minus;-

Inline-block: unordered list

&minus;-

**&gt;**

**&lt;**

**style**

**&gt;**

li

{

display : inline-block;

background : lightblue;

padding:10px;

border-width:2px;

border-color:black;

border-style:solid;

}

**&lt;**

**/style**

**&gt;**

**ul**

**&lt;**

**&gt;**

**&lt;**

**li**

**&gt;**

First Element

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

Second Element

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

Third Element

**&lt;**

**/li**

**&gt;**

**&lt;**

**/ul**

**&gt;**

> **none**
>
> An element that is given the none value to its display property will
> not be displayed at all.
>
> For example let&apos;s create a div-element that has an id of myDiv:

**&lt;**

**div**

id

=

&quot;myDiv&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> This can now be marked as not being displayed by the following CSS
> rule:

#myDiv

{

**display**

:

none

;

}

  -----------------------------------------------------------------------
  **display**                               :     none
  ----------------------------------------- ----- -----------------------

  -----------------------------------------------------------------------

> When an element has been set to be ; the browser ignores every other
> layout property for that specific element (both position and float).
> No box will be rendered for that element and its existence in html
> does not affect the position of following elements.

  -----------------------------------------------------------------------
  **visibility**                          :   hidden
  --------------------------------------- --- ---------------------------

  -----------------------------------------------------------------------

> Note that this is different from setting the visibility property to
> hidden. Setting ; for an element would not display the element on the
> page but the element would still take up the space in the rendering
> process as if it would be visible. This will therefore affect how
> following elements are displayed on the page.
>
> The none value for the display property is commonly used along with
> JavaScript to show or hide elements at will, eliminating the need to
> actually delete and re-create them.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 23.2: To get old table structure using div
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> This is the normal HTML table structure

**&lt;**

**style**

**&gt;**

table {

width: 100%;

}

**&lt;**

**/style**

**&gt;**

**&lt;**

**table**

**&gt;**

**&lt;**

**tr**

**&gt;**

**&lt;**

**td**

**&gt;**

I&apos;m a table

**&lt;**

**/td**

**&gt;**

**&lt;**

**/tr**

**&gt;**

**&lt;**

**/table**

**&gt;**

> You can do same implementation like this

**&lt;**

**style**

**&gt;**

.table-div

{

display: table;

}

.table-row-div

{

display: table-row;

}

.table-cell-div

{

display: table-cell;

}

**&lt;**

**/style**

**&gt;**

**&lt;**

**div**

class

=

&quot;table-div&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;table-row-div&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;table-cell-div&quot;

**&gt;**

I behave like a table now

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
# Chapter 24: Grid
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Grid layout is a new and powerful CSS layout system that allows to
> divide a web page content into rows and columns in an easy way.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 24.1: Basic Example
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> **Property Possible Values** display grid / inline-grid
>
> The CSS Grid is defined as a display property. It applies to a parent
> element and its immediate children only.
>
> Consider the following markup:

**&lt;**

**section**

class

=

&quot;container&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;item1&quot;

**&gt;**

item1

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&quot;item2&quot;

**&gt;**

item2

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&quot;item3&quot;

**&gt;**

item3

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&quot;item4&quot;

**&gt;**

item4

**&lt;**

**/div**

**&gt;**

**&lt;**

**/section**

**&gt;**

> The easiest way to define the markup structure above as a grid is to
> simply set its display property to grid:

.container

{

**display**

:

grid

;

}

> However, doing this will invariably cause all the child elements to
> collapse on top of one another. This is because the children do not
> currently know how to position themselves within the grid. But we can
> explicitly tell them.
>
> First we need to tell the grid element .container how many rows and
> columns will make up its structure and we can do this using the
> grid-columns and grid-rows properties (note the pluralisation):

.container

{

**display**

:

grid

;

**grid-columns**

:

50

px

50

px

50

px

;

**grid-rows**

:

50

px

50

px

;

}

> However, that still doesn&apos;t help us much because we need to give an
> order to each child element. We can do this by specifying the grid-row
> and grid-column values which will tell it where it sits in the grid:

.container

.item1

{

**grid-column**

:

1

;

**grid-row**

:

1

;

}

.container

.item2

{

**grid-column**

:

2

;

**grid-row**

:

1

;

}

.container

.item3

{

**grid-column**

:

1

;

**grid-row**

:

2

;

}

.container

.item4

{

**grid-column**

:

2

;

**grid-row**

:

2

;

}

> By giving each item a column and row value it identifies the items
> order within the container.
>
> View a working example on
> &lbrack;&lbrack;JSFiddle&rbrack;&rbrack;(https://jsfiddle.net/fexfwkkv/3/). You&apos;ll
> need to view this in IE10, IE11 or Edge for it to work as these are
> currently the only browsers supporting Grid Layout (with vendor prefix
> -ms-) or enable a flag in Chrome, Opera and Firefox according to
> &lbrack;&lbrack;caniuse&rbrack;&rbrack;(http://caniuse.com/#feat=css-grid) in order to
> test with them.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
# Chapter 25: Tables
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 25.1: table-layout
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The table-layout property changes the algorithm that is used for the
> layout of a table.

  -----------------------------------------------------------------------
  **width**                     :     150px
  ----------------------------- ----- -----------------------------------

  -----------------------------------------------------------------------

> Below an example of two tables both set to :

!&lbrack;&rbrack;(./images/image200.jpg){width="4.625in" height="1.125in"}

  ------------------------------------------------------------------------------------------
  **table-layout**   :   auto   while the one on the right    **table-layout**   :   fixed
                                has                                                  
  ------------------ --- ------ ----------------------------- ------------------ --- -------

  ------------------------------------------------------------------------------------------

> The table on the left has . The former is
>
> wider than the specified width (210px instead of 150px) but the
> contents fit. The latter takes the defined width of 150px, regardless
> if the contents overflow or not.

**Value Description**

*auto* This is the default value. It defines the layout of the table to
be determined by the contents of its&apos; cells.

> This value sets the table layout to be determined by the width
> property provided to the table. If the content
>
> fixed of a cell exceeds this width, the cell will not resize but
> instead, let the content overflow.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 25.2: empty-cells
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The empty-cells property determines if cells with no content should be
> displayed or not. This has no effect unless border-collapse is set to
> separate.
>
> Below an example with two tables with different values set to the
> empty-cells property:

!&lbrack;&rbrack;(./images/image201.jpg){width="5.708333333333333in"
height="0.8854166666666666in"}

  -----------------------------------------------------------------------------------------
  **empty-cells**   :   show   while the one on the right has  **empty-cells**   :   hide
  ----------------- --- ------ ------------------------------- ----------------- --- ------

  -----------------------------------------------------------------------------------------

> The table on the left has . The former does display the empty cells
> whereas the latter does not.

**Value Description**

> *show* This is the default value. It shows cells even if they are
> empty. hide This value hides a cell altogether if there are no
> contents in the cell.
>
> More Information:
>
> &lbrack;&lbrack;https://www.w3.org/TR/CSS21/tables.html#empty-cells&rbrack;&rbrack;(https://www.w3.org/TR/CSS21/tables.html#empty-cells)
> &lbrack;&lbrack;https://developer.mozilla.org/en-US/docs/Web/CSS/empty-cells&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/empty-cells)
> &lbrack;&lbrack;http://codepen.io/SitePoint/pen/yfhtq&rbrack;&rbrack;(http://codepen.io/SitePoint/pen/yfhtq)

&lbrack;&lbrack;https://css-tricks.com/almanac/properties/e/empty-cells/&rbrack;&rbrack;(https://css-tricks.com/almanac/properties/e/empty-cells/)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 25.3: border-collapse
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The border-collapse property determines if a tables&apos; borders should
> be separated or merged.
>
> Below an example of two tables with different values to the
> border-collapse property:

!&lbrack;&rbrack;(./images/image202.jpg){width="5.666666666666667in"
height="0.9270833333333334in"}

  --------------------------------------------------------------------------------------------------
  **border-collapse**   :   separate   while the one on the     **border-collapse**   :   collapse
                                       right has                                          
  --------------------- --- ---------- ------------------------ --------------------- --- ----------

  --------------------------------------------------------------------------------------------------

> The table on the left has .

**Value Description**

> separate This is the default value. It makes the borders of the table
> separate from each other. collapse This value sets the borders of the
> table to merge together, rather than being distinct.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 25.4: border-spacing
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The border-spacing property determines the spacing between cells. This
> has no effect unless border-collapse is set to separate.
>
> Below an example of two tables with different values to the
> border-spacing property:

!&lbrack;&rbrack;(./images/image203.jpg){width="6.03125in" height="1.15625in"}

  -----------------------------------------------------------------------------------------------
  **border-spacing**   :   2px   (default) while the one on the    **border-spacing**   :   8px
                                 right has                                                  
  -------------------- --- ----- --------------------------------- -------------------- --- -----

  -----------------------------------------------------------------------------------------------

> The table on the left has .

**Value Description**

*&lt;length&gt;* This is the default behavior, though the exact value can
vary between browsers.

> &lt;length&gt; &lt;length&gt; This syntax allows specifying separate
> horizontal and vertical values respectively.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 25.5: caption-side
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

  -----------------------------------------------------------------------
  **&lt;caption**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> The caption-side property determines the vertical positioning of the
> **&gt;** element within a table. This has no effect if such element does
> not exist.
>
> Below an example with two tables with different values set to the
> caption-side property:

!&lbrack;&rbrack;(./images/image204.jpg){width="5.729166666666667in"
height="1.1458333333333333in"}

  ------------------------------------------------------------------------------------------
  **caption-side**   :   top   while the one on the right    **caption-side**   :   bottom
                               has                                                  
  ------------------ --- ----- ----------------------------- ------------------ --- --------

  ------------------------------------------------------------------------------------------

> The table on the left has .

**Value Description**

> *top* This is the default value. It places the caption above the
> table. bottom This value places the caption below the table.

# Chapter 26: Transitions

**Parameter Details**

> The specific CSS property whose value change needs to be transitioned
> (or) all, if all the transition-property &lbrack;&lbrack;transitionable
> properties&rbrack;&rbrack;(https://www.w3.org/TR/css3-transitions/#animatable-properties)
> need to be transitioned.
>
> The duration (or period) in seconds (s) or milliseconds (ms) over
> which the transition transition-duration must take place.

  -----------------------------------------------------------------------
  cubic-bezier                               (),        steps
  ------------------------------------------ ---------- -----------------

  -----------------------------------------------------------------------

> A function that describes how the intermediate values during the
> transition are calculated. Commonly used values are ease, ease-in,
> ease-out, ease-in-out, linear, transition-timing-function
>
> (). More information about the various timing functions can be
>
> found in the &lbrack;&lbrack;W3C
> specs&rbrack;&rbrack;(https://www.w3.org/TR/css3-transitions/#transition-timing-function).
>
> The amount of time that must have elapsed before the transition can
> start. Can be transition-delay
>
> specified in seconds (s) or milliseconds (ms)

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 26.1: Transition shorthand
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>CSS</h4>

div

{

**width**

:

150

px

;

**height**

:

150

px

;

**background-color**

:

red

;

**transition**

:

background-color

1

s

;

}

div

:

hover

{

**background-color**

:

green

;

}

> <h4>HTML</h4>

**&lt;**

**div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> This example will change the background color when the div is hovered
> the background-color change will last 1 second.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 26.2: cubic-bezier
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> The cubic-bezier function is a transition timing function which is
> often used for custom and smooth transitions.

  --------------------------------------------------------------------------------------------
  **transition-timing-function**   :   cubic-bezier    (   0.1   ,   0.7   ,   1.0   ,   0.1
  -------------------------------- --- --------------- --- ----- --- ----- --- ----- --- -----

  --------------------------------------------------------------------------------------------

> );
>
> The function takes four parameters:

  ----------------------------------------------------------------------------------
  cubic-bezier             (   P1_x     ,   P1_y       ,   P2_x       ,   P2_y
  ------------------------ --- -------- --- ---------- --- ---------- --- ----------

  ----------------------------------------------------------------------------------

> )

!&lbrack;&rbrack;(./images/image205.jpg){width="4.395833333333333in"
height="2.2083333333333335in"}

> These parameters will be mapped to points which are part of a &lbrack;&lbrack;Bézier
> curve&rbrack;&rbrack;(https://en.wikipedia.org/wiki/B%C3%A9zier_curve#Cubic_B.C3.A9zier_curves):

!&lbrack;&rbrack;(./images/image206.jpg){width="4.96875in"
height="4.958333333333333in"}

> For CSS Bézier Curves, P0 and P3 are always in the same spot. P0 is at
> (0,0) and P3 is at (1,1), which menas that the parameters passed to
> the cubic-bezier function can only be between 0 and 1.
>
> If you pass parameters which aren&apos;t in this interval the function
> will default to a linear transition.
>
> Since cubic-bezier is the most flexible transition in CSS, you can
> translate all other transition timing function to cubic-bezier
> functions:

  -----------------------------------------------------------------------
  cubic-bezier
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> linear: (0,0,1,1)

  ------------------------------------------------------------------------------
  cubic-bezier               (   0.42     ,   0.0      ,   1.0      ,   1.0
  -------------------------- --- -------- --- -------- --- -------- --- --------

  ------------------------------------------------------------------------------

  -------------------------------------------------------------------------------
  cubic-bezier               (   0.0    ,   0.0      ,   0.58        ,   1.0
  -------------------------- --- ------ --- -------- --- ----------- --- --------

  -------------------------------------------------------------------------------

  -------------------------------------------------------------------------------
  cubic-bezier              (   0.42     ,   0.0      ,   0.58       ,   1.0
  ------------------------- --- -------- --- -------- --- ---------- --- --------

  -------------------------------------------------------------------------------

ease-in: ) ease-out: ) ease-in-out: )

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 26.3: Transition (longhand)
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>CSS</h4>

div

{

**height**

:

100

px

;

**width**

:

100

px

;

**border**

:

1

px

solid

;

**transition-property**

:

height

,

width

;

**transition-duration**

:

1

s

,

500

ms

;

**transition-timing-function**

:

linear

;

**transition-delay**

:

0

s

,

1

s

;

}

div

:

hover

{

**height**

:

200

px

;

**width**

:

200

px

;

}

> <h4>HTML</h4>
>
> **&lt;div&gt;&lt;/div&gt;**
>
> **transition-property**: Specifies the CSS properties the transition
> effect is for. In this case, the div will expand both horizontally and
> vertically when hovered.
>
> **transition-duration**: Specifies the length of time a transition
> takes to complete. In the above example, the height and width
> transitions will take 1 second and 500 milliseconds respectively.
>
> **transition-timing-function**: Specifies the speed curve of the
> transition effect. A *linear* value indicates the transition will have
> the same speed from start to finish.
>
> **transition-delay**: Specifies the amount of time needed to wait
> before the transition effect starts. In this case, the height will
> start transitioning immediately, whereas the width will wait 1 second.

<h2 id="ch27">Chapter 27: Animations</h2>

| &gt;             |                                                      |
| *Transition** |                                                      |
| Parameter     | > Details                                            |
|---------------|------------------------------------------------------|
| property      | > Either the CSS property to transition on, or all,  |
|               | > which specifies all transition-able properties.    |
|---------------|------------------------------------------------------|
| duration      | > Transition time, either in seconds or              |
|               | > milliseconds.                                      |
|---------------|------------------------------------------------------|
| ti            | > Specifies a function to define how intermediate    |
| ming-function | > values for properties are computed. Common values  |
|               | > are ease, linear, and step-end. Check out the      |
|               | > &lbrack;&lbrack;easing function                                  |
|               | > cheatsheet&rbrack;&rbrack;(http://easings.net/) for  |
|               | > more.                                              |
|---------------|------------------------------------------------------|
| delay         | > Amount of time, in seconds or milliseconds, to     |
|               | > wait before playing the animation.                 |
|---------------|------------------------------------------------------|
|               |                                                      |
|---------------|------------------------------------------------------|
| **            |                                                      |
| &commat;keyframes |                                                      |

  -----------------------------------------------------------------------
  <b>&lt;percentage</b>
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

  -----------------------------------------------------------------------
  10%                        ,        20%
  -------------------------- -------- -----------------------------------

  -----------------------------------------------------------------------

> You can either specify a set time with a percentage value, or two
> percentage values, ie
>
> &lbrack; from &vertbar; to &vertbar; **&gt;** &rbrack;
>
> , for a period of time where the keyframe&apos;s set attributes are set.
>
> block Any amount of CSS attributes for the keyframe.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 27.1: Animations with keyframes
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> For multi-stage CSS animations, you can create CSS &commat;keyframes.
> Keyframes allow you to define multiple animation points, called a
> keyframe, to define more complex animations.
>
> **Basic Example**
>
> In this example, we&apos;ll make a basic background animation that cycles
> between all colors.

**&commat;keyframes**

rainbow-background

{

0

&percnt;

{

**background-color**

:

#ff0000

;

}

8.333

&percnt;

{

**background-color**

:

#ff8000

;

}

16.667

&percnt;

{

**background-color**

:

#ffff00

;

}

25.000

&percnt;

{

**background-color**

:

#80ff00

;

}

33.333

&percnt;

{

**background-color**

:

#00ff00

;

}

41.667

&percnt;

{

**background-color**

:

#00ff80

;

}

50.000

&percnt;

{

**background-color**

:

#00ffff

;

}

58.333

&percnt;

{

**background-color**

:

#0080ff

;

}

66.667

&percnt;

{

**background-color**

:

#0000ff

;

}

75.000

&percnt;

{

**background-color**

:

#8000ff

;

}

83.333

&percnt;

{

**background-color**

:

#ff00ff

;

}

91.667

&percnt;

{

**background-color**

:

#ff0080

;

}

100.00

&percnt;

{

**background-color**

:

#ff0000

;

}

}

.RainbowBackground

{

**animation**

:

rainbow-background

5

s

infinite

;

}

&lbrack;*&lbrack;View Result&rbrack;*&rbrack;(https://jsfiddle.net/s9m3od3p/6/)

> There&apos;s a few different things to note here. First, the actual
> &commat;keyframes syntax.

**&commat;keyframes**

rainbow-background

{

> This sets the name of the animation to rainbow-background.

0

&percnt;

{

**background-color**

:

#ff0000

;

}

> This is the definition for a keyframe within the animation. The first
> part, the 0% in the case, defines where the keyframe is during the
> animation. The 0% implies it is 0% of the total animation time from
> the beginning.
>
> The animation will automatically transition between keyframes. So, by
> setting the next background color at 8.333%, the animation will
> smoothly take 8.333% of the time to transition between those
> keyframes.

.RainbowBackground

{

**animation**

:

rainbow-background

5

s

infinite

;

}

> This code attaches our animation to all elements which have the
> .RainbowBackground class.
>
> The actual animation property takes the following arguments.
>
> **animation-name**: The name of our animation. In this case,
> rainbow-background **animation-duration**: How long the animation will
> take, in this case 5 seconds.
>
> **animation-iteration-count (Optional)**: The number of times the
> animation will loop. In this case, the animation will go on
> indefinitely. By default, the animation will play once.
>
> **animation-delay (Optional)**: Specifies how long to wait before the
> animation starts. It defaults to 0 seconds, and can take negative
> values. For example, -2s would start the animation 2 seconds into its
> loop.
>
> **animation-timing-function (Optional)**: Specifies the speed curve of
> the animation. It defaults to ease, where the animation starts slow,
> gets faster and ends slow.

  ------------------------------------------------------------------------
  **background-color**                           :   #ff0000
  ---------------------------------------------- --- ---------------------

  ------------------------------------------------------------------------

> In this particular example, both the 0% and 100% keyframes specify {;
> }. Wherever
>
> two or more keyframes share a state, one may specify them in a single
> statement. In this case, the two 0% and 100% lines could be replaced
> with this single line:

0

&percnt;

,

100

&percnt;

{

**background-color**

:

#ff0000

;

}

> **Cross-browser compatibility**
>
> For older WebKit-based browsers, you&apos;ll need to use the vendor prefix
> on both the &commat;keyframes declaration and the animation property, like
> so:

**@-webkit-keyframes**

{

}

&minus;

webkit-animation

:

&period;..

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 27.2: Animations with the transition property
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Useful for simple animations, the CSS transition property allows
> number-based CSS properties to animate between states.

**Example**

.Example

{

**height**

:

100

px

;

**background**

:

#fff

;

}

.Example

:

hover

{

**height**

:

120

px

;

**background**

:

#ff0000

;

}

&lbrack;*&lbrack;View Result&rbrack;*&rbrack;(https://jsfiddle.net/0kcm6rwo/)

> By default, hovering over an element with the .Example class would
> immediately cause the element&apos;s height to jump to 120px and its
> background color to red (#ff0000).
>
> By adding the transition property, we can cause these changes to occur
> over time:

.Example

{

&period;..

**transition**

:

all

400

ms

ease

;

}

&lbrack;*&lbrack;View Result&rbrack;*&rbrack;(https://jsfiddle.net/v2j4ggue/1/)

> The all value applies the transition to all compatible (numbers-based)
> properties. Any compatible property name (such as height or top) can
> be substituted for this keyword.
>
> 400ms specifies the amount of time the transition takes. In this case,
> the element&apos;s change in height will take 400 milliseconds to
> complete.
>
> Finally, the value ease is the animation function, which determines
> how the animation is played. ease means start slow, speed up, then end
> slow again. Other values are linear, ease-out, and ease-in.
>
> **Cross-Browser Compatibility**
>
> The transition property is generally well-supported across all major
> browsers, excepting IE 9. For earlier versions of Firefox and
> Webkit-based browsers, use vendor prefixes like so:

.Example

{

**transition**

:

all

400

ms

ease

;

-moz-transition

:

all

400

ms

ease

;

-webkit-transition

:

all

400

ms

ease

;

}

> *Note:* The transition property can animate changes between any two
> numerical values, regardless of unit. It can also transition between
> units, such as 100px to 50vh. However, it cannot transition between a
> number and a default or automatic value, such as transitioning an
> element&apos;s height from 100px to auto.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 27.3: Syntax Examples
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Our first syntax example shows the animation shorthand property using
> all of the available properties/parameters:
>
> **animation**: 3s ease-in 1s 2 reverse both paused slidein;
>
> */&ast; duration &vertbar; timing-function &vertbar; delay &vertbar; iteration-count &vertbar;
> direction &vertbar; fill-mode &vertbar; playstate &vertbar; name &ast;/*
>
> Our second example is a little more simple, and shows that some
> properties can be omitted:
>
> **animation**: 3s linear 1s slidein; */&ast; duration &vertbar; timing-function
> &vertbar; delay &vertbar; name &ast;/*
>
> Our third example shows the most minimal declaration. Note that the
> animation-name and animation-duration must be declared:

**animation**

:

3

s

slidein

;

*/&ast; duration &vertbar; name &ast;/*

> It&apos;s also worth mentioning that when using the animation shorthand
> the order of the properties makes a difference. Obviously the browser
> may confuse your duration with your delay.
>
> If brevity isn&apos;t your thing, you can also skip the shorthand property
> and write out each property individually:

**animation-duration**

:

3

s

;

**animation-timing-function**

:

ease-in

;

**animation-delay**

:

1

s

;

**animation-iteration-count**

:

2

;

**animation-direction**

:

reverse

;

**animation-fill-mode**

:

both

;

**animation-play-state**

:

paused

;

**animation-name**

:

slidein

;

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 27.4: Increasing Animation Performance Using the &apos;will-change&apos; Attribute
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> When creating animations and other GPU-heavy actions, it&apos;s important
> to understand the will-change attribute.
>
> Both CSS keyframes and the transition property use GPU acceleration.
> Performance is increased by offloading calculations to the device&apos;s
> GPU. This is done by creating paint layers (parts of the page that are
> individually rendered) that are offloaded to the GPU to be calculated.
> The will-change property tells the browser what will animate, allowing
> the browser to create smaller paint areas, thus increasing
> performance.
>
> The will-change property accepts a comma-separated list of properties
> to be animated. For example, if you plan on transforming an object and
> changing its opacity, you would specify:

.Example

{

&period;..

**will-change**

:

transform

,

opacity

;

}

> **Note:** Use will-change sparingly. Setting will-change for every
> element on a page can cause performance problems, as the browser may
> attempt to create paint layers for every element, significantly
> increasing the amount of processing done by the GPU.

# Chapter 28: 2D Transforms

**Function/Parameter Details**

  -----------------------------------------------------------------------
  rotate
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

&lpar;x&rpar; Defines a transformation that moves the element around a fixed
point on the Z axis

  -----------------------------------------------------------------------
  translate
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

(x,y) Moves the position of the element on the X and Y axis

  -----------------------------------------------------------------------
  translateX
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

(x) Moves the position of the element on the X axis

  -----------------------------------------------------------------------
  translateY
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

(y) Moves the position of the element on the Y axis

  -----------------------------------------------------------------------
  scale
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

(x,y) Modifies the size of the element on the X and Y axis

  -----------------------------------------------------------------------
  scaleX
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

  -----------------------------------------------------------------------
  scaleY
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> &lpar;x&rpar; Modifies the size of the element on the X axis (y) Modifies the
> size of the element on the Y axis

  -----------------------------------------------------------------------
  skew
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> Shear mapping, or transvection, distorting each point of an element by
> a certain angle in
>
> (x,y) each direction

  -----------------------------------------------------------------------
  skewX
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> Horizontal shear mapping distorting each point of an element by a
> certain angle in the

(x) horizontal direction

  -----------------------------------------------------------------------
  skewY
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> Vertical shear mapping distorting each point of an element by a
> certain angle in the vertical

(y) direction

  -----------------------------------------------------------------------
  matrix
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

() Defines a 2D transformation in the form of a transformation matrix.

  -----------------------------------------------------------------------
  skew
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> The angle by which the element should be rotated or skewed (depending
> on the function with which it is used). Angle can be provided in
> degrees (deg), gradians (grad), radians (rad) angle or turns (turn).
> In () function, the second angle is optional. If not provided, there
> will be no (0) skew in Y-axis.
>
> The distance expressed as a length or a percentage by which the
> element should be

  -----------------------------------------------------------------------
  translate
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> length-or-percentage translated. In () function, the second
> length-or-percentage is optional. If not provided, then there would be
> no (0) translation in Y-axis.
>
> A number which defines how many times the element should be scaled in
> the specified axis.

  -----------------------------------------------------------------------
  scale
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> scale-factor In () function, the second scale-factor is optional. If
> not provided, the first scale-factor will be applied for Y-axis also.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 28.1: Rotate
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> <h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;rotate&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.rotate

{

**width**

:

100

px

;

**height**

:

100

px

;

**background**

:

teal

;

**transform**

:

rotate

(

45

deg

)

;

}

> This example will rotate the div by 45 degrees clockwise. The center
> of rotation is in the center of the div, 50% from left and 50% from
> top. You can change the center of rotation by setting the
> transform-origin property.

**transform-origin**

:

100

&percnt;

50

&percnt;

;

> The above example will set the center of rotation to the middle of the
> right side end.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 28.2: Scale
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;scale&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

<h4>CSS</h4>

.scale

{

**width**

:

100

px

;

**height**

:

100

px

;

**background**

:

teal

;

**transform**

:

scale

(

0.5

,

1.3

)

;

}

  --------------------------------------------------------------------------------------
  100px   &ast;   0.5    =   50px   on the X axis and to    100px   &ast;   1.3    =   130px
  ------- ---- ------ --- ------ ----------------------- ------- ---- ------ --- -------

  --------------------------------------------------------------------------------------

> This example will scale the div to on the Y axis.
>
> The center of the transform is in the center of the div, 50% from left
> and 50% from top.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 28.3: Skew
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;skew&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.skew

{

**width**

:

100

px

;

**height**

:

100

px

;

**background**

:

teal

;

**transform**

:

skew

(

20

deg

,

-30

deg

)

;

}

> This example will skew the div by 20 degrees on the X axis and by - 30
> degrees on the Y axis.
>
> The center of the transform is in the center of the div, 50% from left
> and 50% from top.

See the result
&lbrack;&lbrack;here&rbrack;&rbrack;(https://jsfiddle.net/MadalinaTn/gtt4osms/1/).

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
## Section 28.4: Multiple transforms
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

> Multiple transforms can be applied to an element in one property like
> this:

**transform**

:

rotate

(

15

deg

)

translateX

(

200

px

)

;

> This will rotate the element 15 degrees clockwise and then translate
> it 200px to the right.
>
> In chained transforms, **the coordinate system moves with the
> element**. This means that the translation won&apos;t be horizontal but on
> an axis rotate 15 degrees clockwise as shown in the following image:

!&lbrack;&rbrack;(./images/image207.jpg){width="7.48037510936133in"
height="2.7919728783902014in"}

> Changing the order of the transforms will change the output. The first
> example will be different to

**transform**

:

translateX

(

200

px

)

rotate

(

15

deg

)

;

**&lt;**

**div**

class

=

&quot;transform&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.transform

{

**transform**

:

rotate

(

15

deg

)

translateX

(

200

px

)

;

}

> As shown in this image:

!&lbrack;&rbrack;(./images/image208.jpg){width="7.48037510936133in"
height="2.7919728783902014in"}

## Section 28.5: Translate

> <h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;translate&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.translate

{

**width**

:

100

px

;

**height**

:

100

px

;

**background**

:

teal

;

**transform**

:

translate

(

200

px

,

50

&percnt;

)

;

}

  ------------------------------------------------------------------------
  100px                   &ast;   50%                 =   50px
  ----------------------- ---- ------------------- --- -------------------

  ------------------------------------------------------------------------

> This example will move the div by 200px on the X axis and by on the Y
> axis.
>
> You can also specify translations on a single axis.
>
> On the X axis:

.translate

{

**transform**

:

translateX

(

200

px

)

;

}

> On the Y axis:

.translate

{

**transform**

:

translateY

(

50

&percnt;

)

;

}

## Section 28.6: Transform Origin

> Transformations are done with respect to a point which is defined by
> the transform-origin property.

  ------------------------------------------------------------------------
  **transform-origin**                                   :   X Y
  ------------------------------------------------------ --- -------------

  ------------------------------------------------------------------------

> The property takes 2 values : ;

  -----------------------------------------------------------------------
  **transform-origin**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

  ------------------------------------------------------------------------
  **transform-origin**                              :   100%
  ------------------------------------------------- --- ------------------

  ------------------------------------------------------------------------

> In the following example the first div (.tl) is rotate around the top
> left corner with : 0 0; and the second (.tr)is transformed around
> it&apos;s top right corner with 0. The rotation is applied **on hover** :
>
<h4>HTML:</h4>

```
**&lt;**
**div**
class
=
&quot;transform originl&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
**&lt;**
**div**
class
=
&quot;transform origin2&quot;
**&gt;**
**&lt;**
**/div**
**&gt;**
```

<h4>CSS:</h4>

```
.transform
{
**display**
:
inline-block
;
**width**
:
200
px
;
**height**
:
100
px
;
**background**
:
teal
;
**transition**
:
transform
1
s
;
}
.origin1
{
**transform-origin**
:
0
0
;
}
.origin2
{
**transform-origin**
:
100
&percnt;
0
;
}
.transform
:
hover
{
**transform**
:
rotate
(
30
deg
)
;
}
```

> The default value for the transform-origin property is which is the
> center of the element.

<h2 id="ch29">Chapter 29: 3D Transforms</h2>

<h3 id="ch29-1">Section 29.1: Compass pointer or needle shape using 3D transforms</h3>

<h4>CSS</h4>

```
div
.needle
{
**margin**
:
100
px
;
**height**
:
150
px
;
**width**
:
150
px
;
**transform**
:
rotateY
(
85
deg
)
rotateZ
(
45
deg
)
;
*/&ast; presentational &ast;/*
**background-image**
:
linear-gradient
(
to
top
left
,
#555
0
&percnt;
,
#555
40
&percnt;
,
#444
50
&percnt;
,
#333
97
&percnt;
)
;
**box-shadow**
:
inset
6
px
6
px
22
px
8
px
#272727
;
}
```

<h4>HTML</h4>

```
**&lt;**
**div**
class
=
&apos;needle&apos;
**&gt;**
**&lt;**
**/div**
**&gt;**
```

> In the above example, a needle or compass pointer shape is created
> using 3D transforms. Generally when we apply the rotate transform on
> an element, the rotation happens only in the Z-axis and at best we
> will end up with diamond shapes only. But when a rotateY transform is
> added on top of it, the element gets squeezed in the Y-axis and thus
> ends up looking like a needle. The more the rotation of the Y-axis the
> more squeezed the element looks.

  rotateX           (   85deg        )   rotateZ              (   45deg
  ----------------- --- ------------ --- -------------------- --- ------------

> The output of the above example would be a needle resting on its tip.
> For creating a needle that is resting on its base, the rotation should
> be along the X-axis instead of along Y-axis. So the transform
> property&apos;s value would have to be something like );.
>
> &lbrack;&lbrack;This pen&rbrack;&rbrack;(http://codepen.io/hari_shanx/pen/YXzoBo) uses
> a similar approach to create something that resembles the Safari logo
> or a compass dial.
>
> **Screenshot of element with no transform:**

!&lbrack;&rbrack;(./images/image209.jpg){width="1.6979166666666667in"
height="1.6979166666666667in"}

> **Screenshot of element with only 2D transform:**

!&lbrack;&rbrack;(./images/image210.jpg){width="2.3541666666666665in"
height="2.3645833333333335in"}

> **Screenshot of element with 3D transform:**

!&lbrack;&rbrack;(./images/image211.jpg){width="0.7395833333333334in"
height="2.4791666666666665in"}

<h3 id="ch29-2">Section 29.2: 3D text eect with shadow</h3>

<h4>HTML:</h4>

```
**&lt;**
**div**
id
=
&quot;title&quot;
**&gt;**
**&lt;**
**h**
**1**
data-content
=
&quot;HOVER&quot;
**&gt;**
HOVER
**&lt;**
**/h**
**1**
**&gt;**
**&lt;**
**/div**
**&gt;**
```

<h4>CSS:</h4>

```
&ast;
{
**margin**
:
0
;
**padding**
:
0
;
}
html
,
body
{
**height**
:
100
&percnt;
;
**width**
:
100
&percnt;
;
**overflow**
:
hidden
;
**background**
:
#0099CC
;
}
#title
{
**position**
:
absolute
;
**top**
:
50
&percnt;
;
**left**
:
50
&percnt;
;
**transform**
:
translate
(
-50
&percnt;
,
-50
&percnt;
)
;
**perspective-origin**
:
50
&percnt;
50
&percnt;
;
**perspective**
:
300
px
;
}
h1
{
**text-align**
:
center
;
**font-size**
:
12
vmin
;
**font-family**
:
&apos;Open Sans&apos;
,
sans-serif
;
**color**
:
rgba
(
0
,
0
,
0
,
0.8
)
;
**line-height**
:
1
em
;
**transform**
:
rotateY
(
50
deg
)
;
**perspective**
:
150
px
;
**perspective-origin**
:
0
&percnt;
50
&percnt;
;
}
h1
:
after
{
**content**
:
attr
(
data-content
)
;
**position**
:
absolute
;
**left**
:
0
;
**top**
:
0
;
**transform-origin**
:
50
&percnt;
100
&percnt;
;
**transform**
:
rotateX
(
-90
deg
)
;
**color**
:
#0099CC
;
}
#title
:
before
{
**content**
:
&apos;&apos;
;
**position**
:
absolute
;
**top**
:
-150
&percnt;
;
**left**
:
-25
&percnt;
;
**width**
:
180
&percnt;
;
**height**
:
328
&percnt;
;
**background**
:
rgba
(
255
,
255
,
255
,
0.7
)
;
**transform-origin**
:
0
100
&percnt;
;
**transform**
:
translatez
(
-200
px
)
rotate
(
40
deg
)
skewX
(
35
deg
)
;
**border-radius**
:
0
0
100
&percnt;
0
;
}
```

&lbrack;&lbrack;View example with additional hover
effect&rbrack;&rbrack;(http://codepen.io/web-tiki/pen/azeKNy)

!&lbrack;&rbrack;(./images/image212.jpg){width="7.48037510936133in"
height="3.642194881889764in"}

> In this example, the text is transformed to make it look like it is
> going into the screen away from the user.
>
> The shadow is transformed accordingly so it follows the text. As it is
> made with a pseudo element and the data attribute, it inherits the
> transforms form it&apos;s parent (the H1 tag).
>
> The white &quot;light&quot; is made with a pseudo element on the #title
> element. It is skewed and uses border-radius for the rounded corner.

## Section 29.3: backface-visibility

> The backface-visibility property relates to 3D transforms.
>
> With 3D transforms and the backface-visibility property, you&apos;re able
> to rotate an element such that the original front of an element no
> longer faces the screen.
>
> For example, this would flip an element away from the screen:

&lbrack;&lbrack;JSFIDDLE&rbrack;&rbrack;(https://jsfiddle.net/3z3z843c/)

**&lt;**

**div**

class

=

&quot;flip&quot;

**&gt;**

Loren ipsum

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&quot;flip back&quot;

**&gt;**

Lorem ipsum

**&lt;**

**/div**

**&gt;**

.flip

{

-webkit-transform

:

rotateY

(

180

deg

)

;

-moz-transform

:

rotateY

(

180

deg

)

;

-ms-transform

:

rotateY

(

180

deg

)

;

-webkit-backface-visibility

:

visible

;

-moz-backface-visibility

:

visible

;

-ms-backface-visibility

:

visible

;

}

.flip

.back

{

-webkit-backface-visibility

:

hidden

;

-moz-backface-visibility

:

hidden

;

-ms-backface-visibility

:

hidden

;

}

> Firefox 10+ and IE 10+ support backface-visibility without a prefix.
> Opera, Chrome, Safari, iOS, and Android all need
> -webkit-backface-visibility.
>
> It has 4 values:

1.  **visible** (default) - the element will always be visible even when
    not facing the screen.

2.  **hidden** - the element is not visible when not facing the screen.

3.  **inherit** - the property will gets its value from the its parent
    element

4.  **initial** - sets the property to its default, which is visible

## Section 29.4: 3D cube

> 3D transforms can be use to create many 3D shapes. Here is a simple 3D
> CSS cube example:
>
> *HTML:*

**&lt;**

**div**

class

=

&quot;cube&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;cubeFace&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&quot;cubeFace face2&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> *CSS:*

body

{

**perspective-origin**

:

50

&percnt;

100

&percnt;

;

**perspective**

:

1500

px

;

**overflow**

:

hidden

;

}

.cube

{

**position**

:

relative

;

**padding-bottom**

:

20

&percnt;

;

**transform-style**

:

preserve-3d

;

**transform-origin**

:

50

&percnt;

100

&percnt;

;

**transform**

:

rotateY

(

45

deg

)

rotateX

(

0

)

;

}

.cubeFace

{


!&lbrack;&rbrack;(./images/image213.png){width="7.486667760279965in"
height="6.386666666666667in"}

<a href="http://codepen.io/web-tiki/pen/NNwqBa">View this example</a>

> Additional styling is added in the demo and a transform is applied on
> hover to view the 6 faces of the cube.
>
> Should be noted that:
>
> 4 faces are made with pseudo elements chained transforms are applied

<h2 id="ch30">Chapter 30: Filter Property</h2>

> **Value Description** blur(x) Blurs the image by x pixels.
>
> Brightens the image at any value above 1.0 or 100%. Below that, the
> image will be brightness(x) darkened.
>
> Provides more contrast to the image at any value above 1.0 or 100%.
> Below that, the contrast(x) image will get less saturated.
>
> drop-shadow(h, v, x, y, z) Gives the image a drop-shadow. h and v can
> have negative values. x, y, and z are optional.
  | Value         | Description |
  |---------------|------------------------------------------------------|
  | greyscale(x)  | Shows the image in greyscale, with a maximum value of |
  |               | 1.0 or 100%. |
  | hue-rotate(x) | Applies a hue-rotation to the image. |
  | invert(x)     | Inverts the color of the image with a maximum value of |
  |               | 1.0 or 100%. |
  | opacity(x)    | Sets how opaque/transparent the image is with a |
  |               | maximum value of 1.0 or 100%. |
  | saturate(x)   | Saturates the image at any value above 1.0 or 100%. |
  |               | Below that, the image will start to de-saturate. |
  | sepia(x)      | Converts the image to sepia with a maximum value of |
  |               |  1.0 or 100%. |

<h3 id="ch30-1">Section 30.1: Blur</h3>

<h4>HTML</h4>

> **&lt;img** src=&apos;donald-duck.png&apos; alt=&apos;Donald Duck&apos; title=&apos;Donald
> Duck&apos; **/&gt;**
>
> <h4>CSS</h4>

img

{

-webkit-filter

:

blur

(

1

px

)

;

**filter**

:

blur

(

1

px

)

;

}

> **Result**

!&lbrack;&rbrack;(./images/image214.jpg){width="2.2395833333333335in"
height="2.8125in"}

> Makes you wanna rub your glasses.

<h3 id="ch30-2">Section 30.2: Drop Shadow (use box-shadow instead if possible)</h3>

<h4>HTML</h4>

**&lt;**

**p**

**&gt;**

My shadow always follows me.

**&lt;**

**/p**

**&gt;**

> <h4>CSS</h4>

p

{

-webkit-filter

:

drop-shadow

(

10

px

10

px

1

px

green

)

;

**filter**

:

drop-shadow

(

10

px

10

px

1

px

green

)

;

}

> **Result**

!&lbrack;&rbrack;(./images/image215.jpg){width="2.40625in"
height="0.5729166666666666in"}

<h3 id="ch30-3">Section 30.3: Hue Rotate</h3>

<h4>HTML</h4>
>
> **&lt;img** src=&apos;donald-duck.png&apos; alt=&apos;Donald Duck&apos; title=&apos;Donald
> Duck&apos; **/&gt;**
>
> <h4>CSS</h4>

img

{

-webkit-filter

:

hue-rotate

(

120

deg

)

;

**filter**

:

hue-rotate

(

120

deg

)

;

}

> **Result**

!&lbrack;&rbrack;(./images/image216.jpg){width="2.2604166666666665in"
height="2.8125in"}

<h3 id="ch30-4">Section 30.4: Multiple Filter Values</h3>

> To use multiple filters, separate each value with a space.

<h4>HTML</h4>

> **&lt;img** src=&apos;donald-duck.png&apos; alt=&apos;Donald Duck&apos; title=&apos;Donald
> Duck&apos; **/&gt;**

<h4>CSS</h4>

img

{

-webkit-filter

:

brightness

(

200

&percnt;

)

grayscale

(

100

&percnt;

)

sepia

(

100

&percnt;

)

invert

(

100

&percnt;

)

;

**filter**

:

brightness

(

200

&percnt;

)

grayscale

(

100

&percnt;

)

sepia

(

100

&percnt;

)

invert

(

100

&percnt;

)

;

}

> **Result**

!&lbrack;&rbrack;(./images/image217.jpg){width="2.1145833333333335in"
height="2.7083333333333335in"}

<h3 id="ch30-5">Section 30.5: Invert Color</h3>

<h4>HTML</h4>

**&lt;**

**div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

div

{

**width**

:

100

px

;

**height**

:

100

px

;

**background-color**

:

white

;

-webkit-filter

:

invert

(

100

&percnt;

)

;

**filter**

:

invert

(

100

&percnt;

)

;

}

> **Result**

!&lbrack;&rbrack;(./images/image218.jpg){width="1.1979166666666667in"
height="1.1979166666666667in"}

> Turns from white to black.

# Chapter 31: Cursor Styling

## Section 31.1: Changing cursor type

**cursor**

:

value

;

> **Examples:**

**Value Description**

> none No cursor is rendered for the element auto Default. The browser
> sets a cursor help The cursor indicates that help is available wait
> The cursor indicates that the program is busy move The cursor
> indicates something is to be moved pointer The cursor is a pointer and
> indicates a link

## Section 31.2: pointer-events

> The pointer-events property allows for control over how HTML elements
> respond to mouse/touch events.

.disabled

{

**pointer-events**

:

none

;

}

> In this example,

&apos;none&apos; prevents all click, state and cursor options on the specified
HTML element &lbrack;&lbrack;1&rbrack;&rbrack;

> Other valid values for HTMl elements are:
>
> auto; inherit.
>
> 1&period;
> &lbrack;&lbrack;https://css-tricks.com/almanac/properties/p/pointer-events/&rbrack;&rbrack;(https://css-tricks.com/almanac/properties/p/pointer-events/)
>
> Other resources:
>
> &lbrack;&lbrack;https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events)
> &lbrack;&lbrack;https://davidwalsh.name/pointer-events&rbrack;&rbrack;(https://davidwalsh.name/pointer-events)

<h3 id="ch31-3">Section 31.3: caret-color</h3>

> The caret-color CSS property specifies the color of the caret, the
> visible indicator of the insertion point in an element where text and
> other content is inserted by the user&apos;s typing or editing.
>
<h4>HTML</h4>

**&lt;**

**input**

id

=

&quot;example&quot;

**/&gt;**

> <h4>CSS</h4>

#example

{

**caret-color**

:

red

;

}

> Resources:
>
> &lbrack;&lbrack;https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color)

# Chapter 32: box-shadow

**Parameters Details**

> by default, the shadow is treated as a drop shadow. the inset keyword
> draws the shadow inside the inset frame/border.
>
> offset-x the horizontal distance offset-y the vertical distance
>
> 0 by default. value cannot be negative. the bigger the value, the
> bigger and lighter the shadow blur-radius becomes.
>
> 0 by default. positive values will cause the shadow to expand.
> negative values will cause the shadow spread-radius to shrink.

  -----------------------------------------------------------------------------
  rgb()          ,   rgba()            ,   hsl()          ,   hsla()
  -------------- --- ----------------- --- -------------- --- -----------------

  -----------------------------------------------------------------------------

color can be of various notations: a color keyword, hexadecimal,

## Section 32.1: bottom-only drop shadow using a pseudoelement

JSFiddle:
&lbrack;&lbrack;https://jsfiddle.net/UnsungHero97/80qod7aL/2/&rbrack;&rbrack;(https://jsfiddle.net/UnsungHero97/80qod7aL/2/)

> <h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;box_shadow&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.box_shadow

{

**background-color**

:

#1C90F3

;

**width**

:

200

px

;

**height**

:

100

px

;

**margin**

:

50

px

;

}

.box_shadow

:

after

{

**content**

:

&quot;&quot;

;

**width**

:

190

px

;

**height**

:

1

px

;

**margin-top**

:

98

px

;

**margin-left**

:

5

px

;

**display**

:

block

;

**position**

:

absolute

;

**z-index**

:

&minus;

1

;

-webkit-box-shadow

:

0

px

0

px

8

px

2

px

#444444

;

-moz-box-shadow

:

0

px

0

px

8

px

2

px

#444444

;

**box-shadow**

:

0

px

0

px

8

px

2

px

#444444

;

}

!&lbrack;&rbrack;(./images/image220.jpg){width="6.25in" height="3.75in"}

<h3 id="ch32-2">Section 32.2: drop shadow</h3>

JSFiddle:
&lbrack;&lbrack;https://jsfiddle.net/UnsungHero97/80qod7aL/&rbrack;&rbrack;(https://jsfiddle.net/UnsungHero97/80qod7aL/)

<h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;box_shadow&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.box_shadow

{

-webkit-box-shadow

:

0

px

0

px

10

px

-1

px

#444444

;

-moz-box-shadow

:

0

px

0

px

10

px

-1

px

#444444

;

**box-shadow**

:

0

px

0

px

10

px

-1

px

#444444

;

}

<h3 id="ch32-3">Section 32.3: inner drop shadow</h3>

<h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;box_shadow&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.box_shadow

{

**background-color**

:

#1C90F3

;

**width**

:

200

px

;

**height**

:

100

px

;

**margin**

:

50

px

;

-webkit-box-shadow

:

inset

0

px

0

px

10

px

0

px

#444444

;

-moz-box-shadow

:

inset

0

px

0

px

10

px

0

px

#444444

;

**box-shadow**

:

inset

0

px

0

px

10

px

0

px

#444444

;

}

> **Result:**

!&lbrack;&rbrack;(./images/image221.jpg){width="2.6458333333333335in"
height="1.5416666666666667in"}

JSFiddle:
&lbrack;&lbrack;https://jsfiddle.net/UnsungHero97/80qod7aL/1/&rbrack;&rbrack;(https://jsfiddle.net/UnsungHero97/80qod7aL/1/)

<h3 id="ch32-4">Section 32.4: multiple shadows</h3>

JSFiddle:
&lbrack;&lbrack;https://jsfiddle.net/UnsungHero97/80qod7aL/5/&rbrack;&rbrack;(https://jsfiddle.net/UnsungHero97/80qod7aL/5/)

<h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;box_shadow&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.box_shadow

{

**width**

:

100

px

;

**height**

:

100

px

;

**margin**

:

100

px

;

**box-shadow**

:

-52

px

-52

px

0

px

0

px

#f65314

,

52

px

-52

px

0

px

0

px

#7cbb00

,

-52

px

52

px

0

px

0

px

#00a1f1

,

52

px

52

px

0

px

0

px

#ffbb00

;

}

!&lbrack;&rbrack;(./images/image222.jpg){width="6.125in"
height="5.833333333333333in"}

# Chapter 33: Shapes for Floats

**Parameter Details**

> A value of none means that the float area (the area that is used for
> wrapping content around a float none element) is unaffected. This is
> the default/initial value.

  -----------------------------------------------------------------------
  inset     (),   circle      (),   ellipse       () or     polygon
  --------- ----- ----------- ----- ------------- --------- -------------

  -----------------------------------------------------------------------

> Refers to one among (). Using one of these functions and its
> basic-shape values the shape is defined.
>
> Refers to one among margin-box, border-box, padding-box, content-box.
> When only &lt;shape-box&gt; is
>
> shape-box provided (without &lt;basic-shape&gt;) this box *is the* shape.
> When it is used along with &lt;basic-shape&gt;, this acts as the reference
> box.
>
> When an image is provided as value, the shape is computed based on the
> alpha channel of the image image specified.

## Section 33.1: Shape Outside with Basic Shape -- circle()

> With the shape-outside CSS property one can define shape values for
> the float area so that the inline content wraps around the shape
> instead of the float&apos;s box.
>
> <h4>CSS</h4>

img

:

nth-of-type

(

1

)

{

**shape-outside**

:

circle

(

80

px

at

50

&percnt;

50

&percnt;

)

;

**float**

:

left

;

**width**

:

200

px

;

}

img

:

nth-of-type

(

2

)

{

**shape-outside**

:

circle

(

80

px

at

50

&percnt;

50

&percnt;

)

;

**float**

:

right

;

**width**

:

200

px

;

}

p

{

**text-align**

:

center

;

**line-height**

:

30

px

;

*/&ast; purely for demo &ast;/*

}

<h4>HTML</h4>
>
> **&lt;img**
> src=&quot;http://images.clipartpanda.com/circle-clip-art-circlergb.jpg&quot;**&gt;**
>
> **&lt;img**
> src=&quot;http://images.clipartpanda.com/circle-clip-art-circlergb.jpg&quot;**&gt;**
>
> **&lt;p&gt;**Some paragraph whose text content is required to be wrapped
> such that it follows the curve of the circle on either side. And then
> there is some filler text just to make the text long enough. Lorem
> Ipsum Dolor Sit Amet&period;...**&lt;/p&gt;**
>
> In the above example, both the images are actually square images and
> when the text is placed without the shapeoutside property, it will not
> flow around the circle on either side. It will flow around the
> containing box of the image only. With shape-outside the float area is
> re-defined as a *circle* and the content is made to flow around this
> *imaginary circle* that is created using shape-outside.
>
> The *imaginary circle* that is used to re-define the float area is a
> circle with radius of 80px drawn from the center-mid point of the
> image&apos;s reference box.
>
> Below are a couple of screenshots to illustrate how the content would
> be wrapped around when shape-outside is used and when it is not used.
> **Output with shape-outside**

!&lbrack;&rbrack;(./images/image223.jpg){width="3.3333333333333335in"
height="1.3229166666666667in"}

> **Output without shape-outside**

!&lbrack;&rbrack;(./images/image224.jpg){width="3.3333333333333335in"
height="1.4895833333333333in"}

## Section 33.2: Shape margin

> The shape-margin CSS property adds a *margin* to shape-outside.
>
> <h4>CSS</h4>

img

:

nth-of-type

(

1

)

{

**shape-outside**

:

circle

(

80

px

at

50

&percnt;

50

&percnt;

)

;

**shape-margin**

:

10

px

;

**float**

:

left

;

**width**

:

200

px

;

}

img

:

nth-of-type

(

2

)

{

**shape-outside**

:

circle

(

80

px

at

50

&percnt;

50

&percnt;

)

;

**shape-margin**

:

10

px

;

**float**

:

right

;

**width**

:

200

px

;

}

p

{

**text-align**

:

center

;

**line-height**

:

30

px

;

*/&ast; purely for demo &ast;/*

}

<h4>HTML</h4>
>
> **&lt;img**
> src=&quot;http://images.clipartpanda.com/circle-clip-art-circlergb.jpg&quot;**&gt;**
>
> **&lt;img**
> src=&quot;http://images.clipartpanda.com/circle-clip-art-circlergb.jpg&quot;**&gt;**
>
> **&lt;p&gt;**Some paragraph whose text content is required to be wrapped
> such that it follows the curve of the circle on either side. And then
> there is some filler text just to make the text long enough. Lorem
> Ipsum Dolor Sit Amet&period;...**&lt;/p&gt;**
>
> In this example, a 10px margin is added around the **shape** using
> shape-margin. This creates a bit more space between the *imaginary
> circle* that defines the float area and the actual content that is
> flowing around.
>
> **Output:**

!&lbrack;&rbrack;(./images/image225.jpg){width="3.3333333333333335in"
height="1.3958333333333333in"}

# Chapter 34: List Styles

> **Value Description** list-style-type the type of list-item marker.
>
> list-style-position specifies where to place the marker
> list-style-image specifies the type of list-item marker initial sets
> this property to its default value inherit inherits this property from
> its parent element

## Section 34.1: Bullet Position

  ---------------------------------------------------------------------------------------------
  **&lt;li**   **&gt;** elements inside a containing element (       **&lt;ul**   **&gt;**   **&lt;ol**
                                                                            or       
  ---------- --------------------------------------------------- ---------- -------- ----------

  ---------------------------------------------------------------------------------------------

> A list consists of **&gt;**). Both the list items and the container can
>
> have margins and paddings which influence the exact position of the
> list item content in the document. The default values for the margin
> and padding may be different for each browser. In order to get the
> same layout crossbrowser, these need to be set specifically.
>
> Each list item gets a &apos;marker box&apos;, which contains the bullet
> marker. This box can either be placed inside or outside of the list
> item box.

**list-style-position**

:

inside

;

  -----------------------------------------------------------------------
  **&lt;li**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> places the bullet within the **&gt;** element, pushing the content to
> the right as needed.

**list-style-position**

:

outside

;

  -----------------------------------------------------------------------
  **&lt;li**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> places the bullet left of the **&gt;** element. If there is not enough
> space in the padding of the containing element, the marker box will
> extend to the left even if it would fall off the page.
>
> Showing the result of inside and outside positioning:
> &lbrack;&lbrack;jsfiddle&rbrack;&rbrack;(https://jsfiddle.net/pqh3cxdp/)

## Section 34.2: Removing Bullets / Numbers

> Sometimes, a list should just not display any bullet points or
> numbers. In that case, remember to specify margin and padding.

**&lt;**

**ul**

**&gt;**

**&lt;**

**li**

**&gt;**

first item

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

second item

**&lt;**

**/li**

**&gt;**

**&lt;**

**/ul**

**&gt;**

> CSS

ul

{

**list-style-type**

:

none

;

}

li

{

**margin**

:

0

;

**padding**

:

0

;

}

## Section 34.3: Type of Bullet or Numbering

  --------------------------------------------------------------------------------
  **&lt;li**   **&gt;** tags within an unordered list (                     **&lt;ul**
  ---------- ---------------------------------------------------------- ----------

  --------------------------------------------------------------------------------

> Specific for **&gt;**):
>
> **list-style**: disc; */&ast; A filled circle (default) &ast;/*
> **list-style**: circle; */&ast; A hollow circle &ast;/* **list-style**:
> square; */&ast; A filled square &ast;/* **list-style**: &apos;-&apos;; */&ast; any
> string &ast;/*

  -------------------------------------------------------------------------------
  **&lt;li**   **&gt;** tags within an ordered list (                      **&lt;ol**
  ---------- --------------------------------------------------------- ----------

  -------------------------------------------------------------------------------

> Specific for **&gt;**):

**list-style**: decimal; */&ast; Decimal numbers beginning with 1 (default)
&ast;/* **list-style**: decimal-leading-zero;*/&ast; Decimal numbers padded by
initial zeros (01, 02, 03,* ... *10) &ast;/* **list-style**: lower-roman;
*/&ast; Lowercase roman numerals (i., ii., iii., iv., &period;..) &ast;/*
**list-style**: upper-roman; */&ast; Uppercase roman numerals (I., II.,
III., IV., &period;..) &ast;/* **list-style-type**: lower-greek; */&ast; Lowercase
roman letters (*α*.,* β*.,* γ*.,* δ*., &period;..) &ast;/* **list-style-type**:
lower-alpha; */&ast; Lowercase letters (a., b., c., d., &period;..) &ast;/*
**list-style-type**: lower-latin; */&ast; Lowercase letters (a., b., c.,
d., &period;..) &ast;/* **list-style-type**: upper-alpha; */&ast; Uppercase letters
(A., B., C., D., &period;..) &ast;/* **list-style-type**: upper-latin; */&ast;
Uppercase letters (A., B., C., D., &period;..) &ast;/* Non-specific:

> **list-style**: none; */&ast; No visible list marker &ast;/* **list-style**:
> inherit; */&ast; Inherits from parent &ast;/*

<h2 id="ch35">Chapter 35: Counters</h2>

| Para  | &gt; Details                                              |
| meter |                                                            |
|---------|------------------------------------------------------------|
| count   | This is the name of the counter that needs to be created   |
| er-name | or incremented or printed. It can be any custom name as    |
|         | the developer wishes.                                      |
|---------|------------------------------------------------------------|
| integer | This integer is an optional value that when provided next  |
|         | to the counter name will represent the initial value of    |
|         | the counter (in counter-set, counter-reset properties) or  |
|         | the value by which the counter should be incremented (in   |
|         | counter-increment).                                        |

  -----------------------------------------------------------------------
  counter-
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> This is the initial value for all 3 &ast; properties. When this value is
> used for counter-

none increment, the value of none of the counters are affected. When
this is used for the other two, no

> counter is created.
>
> This specifies the style in which the counter value needs to be
> displayed. It supports all values

counter-style supported by the list-style-type property. If none is used
then the counter value is not printed

> at all.
>
> This represents the string that must be placed between the values of
> two different counter levels
>
> connector-string (like the &quot;.&quot; in &quot;2.1.1&quot;).

## Section 35.1: Applying roman numerals styling to the counter output

> <h4>CSS</h4>

body

{

**counter-reset**

:

item-counter

;

}

.item

{

**counter-increment**

:

item-counter

;

}

.item

:

before

{

**content**

:

counter

(

item-counter

,

upper-roman

)

&quot;. &quot;

;

*/&ast; by specifying the upper-roman as style the*

*output would be in roman numbers &ast;/*

}

<h4>HTML</h4>

**&lt;**

**div**

class

=

&apos;item&apos;

**&gt;**

Item No: 1

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&apos;item&apos;

**&gt;**

Item No: 2

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&apos;item&apos;

**&gt;**

Item No: 3

**&lt;**

**/div**

**&gt;**

> In the above example, the counter&apos;s output would be displayed as I,
> II, III (roman numbers) instead of the usual 1, 2, 3 as the developer
> has explicitly specified the counter&apos;s style.

## Section 35.2: Number each item using CSS Counter

> <h4>CSS</h4>

body

{

**counter-reset**

:

item-counter

;

*/&ast; create the counter &ast;/*

}

.item

{

**counter-increment**

:

item-counter

;

*/&ast; increment the counter every time an element with class &quot;item&quot;*

*is encountered &ast;/*

}

.item-header

:

before

{

**content**

:

counter

(

item-counter

)

&quot;. &quot;

;

*/&ast; print the value of the counter before the header and*

*append a &quot;.&quot; to it &ast;/*

}

*/&ast; just for demo &ast;/*

.item

{

**border**

:

1

px

solid

;

**height**

:

100

px

;

**margin-bottom**

:

10

px

;

}

.item-header

{

**border-bottom**

:

1

px

solid

;

**height**

:

40

px

;

**line-height**

:

40

px

;

**padding**

:

5

px

;

}

.item-content

{

**padding**

:

8

px

;

}

<h4>HTML</h4>

**&lt;**

**div**

class

=

&apos;item&apos;

**&gt;**

**&lt;**

**div**

class

=

&apos;item-header&apos;

**&gt;**

Item 1 Header

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&apos;item-content&apos;

**&gt;**

Lorem Ipsum Dolor Sit Amet&period;...

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&apos;item&apos;

**&gt;**

**&lt;**

**div**

class

=

&apos;item-header&apos;

**&gt;**

Item 2 Header

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&apos;item-content&apos;

**&gt;**

Lorem Ipsum Dolor Sit Amet&period;...

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&apos;item&apos;

**&gt;**

**&lt;**

**div**

class

=

&apos;item-header&apos;

**&gt;**

Item 3 Header

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&apos;item-content&apos;

**&gt;**

Lorem Ipsum Dolor Sit Amet&period;...

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

  -----------------------------------------------------------------------
  :before
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> The above example numbers every &quot;item&quot; in the page and adds the
> item&apos;s number before its header (using content property of
> .item-header element&apos;s pseudo). A live demo of this code is available
> &lbrack;&lbrack;here&rbrack;&rbrack;(https://jsfiddle.net/a7rmje3r/).

## Section 35.3: Implementing multi-level numbering using CSS counters

<h4>CSS</h4>

ul

{

**list-style**

:

none

;

**counter-reset**

:

list-item-number

;

*/&ast; self nesting counter as name is same for all levels &ast;/*

}

li

{

**counter-increment**

:

list-item-number

;

}

li

:

before

{

**content**

:

counters

(

list-item-number

,

&quot;.&quot;

)

&quot; &quot;

;

*/&ast; usage of counters() function means value of*

*counters at all higher levels are combined before printing &ast;/*

}

<h4>HTML</h4>

**&lt;**

**ul**

**&gt;**

**&lt;**

**li**

**&gt;**

Level 1

**&lt;**

**ul**

**&gt;**

**&lt;**

**li**

**&gt;**

Level 1.1

**&lt;**

**ul**

**&gt;**

**&lt;**

**li**

**&gt;**

Level 1.1.1

**&lt;**

**/li**

**&gt;**

**&lt;**

**/ul**

**&gt;**

**&lt;**

**/li**

**&gt;**

**&lt;**

**/ul**

**&gt;**

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

Level 2

**&lt;**

**ul**

**&gt;**

**&lt;**

**li**

**&gt;**

Level 2.1

**&lt;**

**ul**

**&gt;**

**&lt;**

**li**

**&gt;**

Level 2.1.1

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

Level 2.1.2

**&lt;**

**/li**

**&gt;**

**&lt;**

**/ul**

**&gt;**

**&lt;**

**/li**

**&gt;**

**&lt;**

**/ul**

**&gt;**

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

Level 3

**&lt;**

**/li**

**&gt;**

**&lt;**

**/ul**

**&gt;**

  ------------------------------------------------------------------------------
  list-item-number   &lbrack;1&rbrack; (counter for second level) and     list-item-number
                     nests it under                           
  ------------------ ---------------------------------------- ------------------

  ------------------------------------------------------------------------------

> The above is an example of multi-level numbering using CSS counters.
> It makes use of the ***self-nesting*** concept of counters. Self
> nesting is a concept where if an element already has a counter with
> the given name but is having to create another then it creates it as a
> child of the existing counter. Here, the second level ul already
> inherits the list-item-number counter from its parent but then has to
> create its own list-item-number (for its children li) and so creates
> &lbrack;0&rbrack; (counter for first level). Thus it achieves the multi-level
> numbering.

  ------------------------------------------------------------------------------
  counters   () function instead of  counter   () function because    counters
             the                               the                    
  ---------- ----------------------- --------- ---------------------- ----------

  ------------------------------------------------------------------------------

> The output is printed using the () function is designed to prefix the
> value of all higher level counters (parent) when printing the output.

# Chapter 36: Functions

## Section 36.1: calc() function

> Accepts a mathematical expression and returns a numerical value.
>
> It is especially useful when working with different types of units
> (e.g. subtracting a px value from a percentage) to calculate the value
> of an attribute.
>
> +, -, /, and &ast; operators can all be used, and parentheses can be
> added to specify the order of operations if necessary.

Use

calc

(

)

to calculate the width of a div element:

#div1

{

**position**

:

absolute

;

**left**

:

50

px

;

**width**

:

calc

(

100

&percnt;

&minus;

100

px

)

;

**border**

:

1

px

solid

black

;

**background-color**

:

yellow

;

**padding**

:

5

px

;

**text-align**

:

center

;

}

  -----------------------------------------------------------------------
  calc
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> Use () to determine the position of a background-image:

**background-position**

:

calc

(

50

&percnt;

&plus;

17

px

)

calc

(

50

&percnt;

&plus;

10

px

)

,

50

&percnt;

50

&percnt;

;

  -----------------------------------------------------------------------
  calc
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> Use () to determine the height of an element:

**height**

:

calc

(

100

&percnt;

&minus;

20

px

)

;

## Section 36.2: attr() function

> Returns the value of an attribute of the selected element.

  -----------------------------------------------------------------------
  data-
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

  -----------------------------------------------------------------------
  ::before                      and             ::after
  ----------------------------- --------------- -------------------------

  -----------------------------------------------------------------------

> Below is a blockquote element which contains a character inside a &ast;
> attribute which CSS can use (e.g. inside the pseudo-element) using
> this function.

**&lt;**

**blockquote**

data-mark

=

&apos;&quot;&apos;

**&gt;**

**&lt;**

**/blockquote**

**&gt;**

> In the following CSS block, the character is appended before and after
> the text inside the element:

blockquote

&lbrack;

data-mark

&rbrack;

::

before

,

blockquote

&lbrack;

data-mark

&rbrack;

::

after

{

**content**

:

attr

(

data-mark

)

;

}

## Section 36.3: var() function

> The var() function allows CSS variables to be accessed.

*/&ast; set a variable &ast;/*

:

root

{

&minus;-

primary-color

:

blue

;

}

*/&ast; access variable &ast;/*

selector

{

**color**

:

var

(

&minus;-

primary-color

)

;

}

> This feature is currently under development. Check
> &lbrack;&lbrack;caniuse.com&rbrack;&rbrack;(http://caniuse.com/#feat=css-variables)
> for the latest browser support.

## Section 36.4: radial-gradient() function

> Creates an image representing a gradient of colors radiating from the
> center of the gradient
>
> radial-gradient(red, orange, yellow) */&ast;A gradient coming out from
> the middle of the gradient, red at the center, then orange, until it
> is finally yellow at the edges&ast;/*

## Section 36.5: linear-gradient() function

> Creates a image representing a linear gradient of colors.

linear-gradient

(

0

deg

,

red

,

yellow

50

&percnt;

,

blue

)

;

> This creates a gradient going from bottom to top, with colors starting
> at red, then yellow at 50%, and finishing in blue.

# Chapter 37: Custom Properties (Variables)

> CSS Variables allow authors to create reusable values which can be
> used throughout a CSS document.
>
> For example, it&apos;s common in CSS to reuse a single color throughout a
> document. Prior to CSS Variables this would mean reusing the same
> color value many times throughout a document. With CSS Variables the
> color value can be assigned to a variable and referenced in multiple
> places. This makes changing values easier and is more semantic than
> using traditional CSS values.

## Section 37.1: Variable Color

:

root

{

&minus;-

red

:

#b00

;

&minus;-

blue

:

#4679bd

;

&minus;-

grey

:

#ddd

;

}

.Bx1

{

**color**

:

var

(

&minus;-

red

)

;

**background**

:

var

(

&minus;-

grey

)

;

**border**

:

1

px

solid

var

(

&minus;-

red

)

;

}

## Section 37.2: Variable Dimensions

:

root

{

&minus;-W200

:

200

px

;

&minus;-

W

10

:

10

px

;

}

.Bx2

{

**width**

:

var

(

&minus;-W200

)

;

**height**

:

var

(

&minus;-W200

)

;

**margin**

:

var

(

&minus;-

W

10

)

;

}

## Section 37.3: Variable Cascading

> CSS variables cascade in much the same way as other properties, and
> can be restated safely.
>
> You can define variables multiple times and only the definition with
> the highest specificity will apply to the element selected.
>
> Assuming this HTML:

**&lt;**

**a**

class

=

&quot;button&quot;

**&gt;**

Button Green

**&lt;**

**/a**

**&gt;**

**&lt;**

**a**

class

=

&quot;button button_red&quot;

**&gt;**

Button Red

**&lt;**

**/a**

**&gt;**

**&lt;**

**a**

class

=

&quot;button&quot;

**&gt;**

Button Hovered On

**&lt;**

**/a**

**&gt;**

> We can write this CSS:

.button

{

&minus;-

color

:

green

;

**padding**

:

.5

rem

;

**border**

:

1

px

solid

var

(

&minus;-

color

)

;

**color**

:

var

(

&minus;-

color

)

;

}

.button

:

hover

{

&minus;-

color

:

blue

;

}

.button_red

{

&minus;-

color

:

red

;

}

> And get this result:

!&lbrack;&rbrack;(./images/image226.jpg){width="3.71875in"
height="0.6041666666666666in"}

## Section 37.4: Valid/Invalids

> **Naming** When naming CSS variables, it contains only letters and
> dashes just like other CSS properties (eg: lineheight,
> -moz-box-sizing) but it should start with double dashes (&minus;-)

//These are Invalids variable names

&minus;-123

color

:

blue

;

&minus;-

&num;

**color**

:

red

;

&minus;-

bg

&lowbar;color

:

yellow

&minus;-

&dollar;

**width**

:

100

px

;

//Valid variable names

&minus;-

color

:

red

;

&minus;-

bg-color

:

yellow

&minus;-

width

:

100

px

;

> **CSS Variables are case sensitive.**

*/&ast; The variable names below are all different variables &ast;/*

&minus;-

pcolor

:

;

&minus;-

Pcolor

:

;

&minus;-

pColor

:

;

> **Empty Vs Space**

*/&ast; Invalid &ast;/*

&minus;-

color

:

;

*/&ast; Valid &ast;/*

&minus;-

color

:

;

*/&ast; space is assigned &ast;/*

> **Concatenations**

*/&ast; Invalid - CSS doesn&apos;t support concatenation&ast;/*

.logo

{

&minus;-

logo-url

:

&apos;logo&apos;

;

**background**

:

url

(

&apos;assets/img/&apos;

var

(

&minus;-

logo-url

)

&apos;.png&apos;

)

;

}

*/&ast; Invalid - CSS bug &ast;/*

.logo

{

&minus;-

logo-url

:

&apos;assets/img/logo.png&apos;

;

**background**

:

url

(

var

(

&minus;-

logo-url

)

)

;

}

*/&ast; Valid &ast;/*

.logo

{

&minus;-

logo-url

:

url

(

&apos;assets/img/logo.png&apos;

)

;

**background**

:

var

(

&minus;-

logo-url

)

;

}

> **Careful when using Units**

*/&ast; Invalid &ast;/*

&minus;-

width

:

10

;

**width**

:

var

(

&minus;-

width

)

px

;

*/&ast; Valid &ast;/*

&minus;-

width

:

10

px

;

**width**

:

var

(

&minus;-

width

)

;

*/&ast; Valid &ast;/*

&minus;-

width

:

10

;

**width**

:

calc

(

1

px

&ast;

var

(

&minus;-

width

)

)

;

*/&ast; multiply by 1 unit to convert &ast;/*

**width**

:

calc

(

1

em

&ast;

var

(

&minus;-

width

)

)

;

<h3 id="ch37-5">Section 37.5: With media queries</h3>

> You can re-set variables within media queries and have those new
> values cascade wherever they are used, something that isn&apos;t possible
> with pre-processor variables.
>
> Here, a media query changes the variables used to set up a very simple
> grid:
>
<h4>HTML</h4>

**&lt;**

**div**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

:

root

{

&minus;-

width

:

25

&percnt;

;

&minus;-

content

:

&apos;This is desktop&apos;

;

}

**&commat;media**

only screen and

(

**max-width**

:

767

px

)

{

:

root

{

&minus;-

width

:

50

&percnt;

;

&minus;-

content

:

&apos;This is mobile&apos;

;

}

}

**&commat;media**

only screen and

(

**max-width**

:

480

px

)

{

:

root

{

&minus;-

width

:

100

&percnt;

;

}

}

div

{

**width**

:

calc

(

var

(

&minus;-

width

)

&minus;

20

px

)

;

**height**

:

100

px

;

}

div

:

before

{

**content**

:

var

(

&minus;-

content

)

;

}

*/&ast; Other Styles &ast;/*

body

{

**padding**

:

10

px

;

}

div

{

**display**

:

flex

;

**align-items**

:

center

;

**justify-content**

:

center

;

**font-weight**

:

bold

;

**float**

:

left

;

**margin**

:

10

px

;

**border**

:

4

px

solid

black

;

**background**

:

red

;

}

> You can try resizing the window in this &lbrack;&lbrack;CodePen
> Demo&rbrack;&rbrack;(https://codepen.io/mkumaran/pen/BZaXvz)
>
> Here&apos;s an animated screenshot of the resizing in action:

!&lbrack;&rbrack;(./images/image227.jpg){width="7.48037510936133in"
height="4.327166447944007in"}

# Chapter 38: Single Element Shapes

## Section 38.1: Trapezoid

> A trapezoid can be made by a block element with zero height (height of
> 0px), a width greater than zero and a border, that is transparent
> except for one side:

!&lbrack;&rbrack;(./images/image228.jpg){width="4.75in" height="1.96875in"}

> **HTML:**

**&lt;**

**div**

class

=

&quot;trapezoid&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> **CSS:**

.trapezoid

{

**width**

:

50

px

;

**height**

:

0

;

**border-left**

:

50

px

solid

transparent

;

**border-right**

:

50

px

solid

transparent

;

**border-bottom**

:

100

px

solid

black

;

}

> With changing the border sides, the orientation of the trapezoid can
> be adjusted.

## Section 38.2: Triangles

> To create a CSS triangle define an element with a width and height of
> 0 pixels. The triangle shape will be formed using border properties.
> For an element with 0 height and width the 4 borders (top, right,
> bottom, left) each form a triangle. Here&apos;s an element with 0
> height/width and 4 different colored borders.

!&lbrack;&rbrack;(./images/image229.jpg){width="1.6666666666666667in"
height="1.7083333333333333in"}

> By setting some borders to transparent, and others to a color we can
> create various triangles. For example, in the Up triangle, we set the
> bottom border to the desired color, then set the left and right
> borders to transparent. Here&apos;s an image with the left and right
> borders shaded slightly to show how the triangle is being formed.

!&lbrack;&rbrack;(./images/image230.jpg){width="1.1458333333333333in"
height="1.1875in"}

> The dimensions of the triangle can be altered by changing the
> different border widths - taller, shorter, lopsided, etc. The examples
> below all show a 50x50 pixel triangle.
>
> **Triangle - Pointing Up**

**&lt;**

**div**

class

=

&quot;triangle-up&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-up

{

**width**

:

0

;

**height**

:

0

;

**border-left**

:

25

px

solid

transparent

;

**border-right**

:

25

px

solid

transparent

;

**border-bottom**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

}

> **Triangle - Pointing Down**

**&lt;**

**div**

class

=

&quot;triangle-down&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-down

{

**width**

:

0

;

**height**

:

0

;

**border-left**

:

25

px

solid

transparent

;

**border-right**

:

25

px

solid

transparent

;

**border-top**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

}

> **Triangle - Pointing Right**

!&lbrack;&rbrack;(./images/image233.jpg){width="1.1458333333333333in"
height="1.1875in"}

**&lt;**

**div**

class

=

&quot;triangle-right&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-right

{

**width**

:

0

;

**height**

:

0

;

**border-top**

:

25

px

solid

transparent

;

**border-bottom**

:

25

px

solid

transparent

;

**border-left**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

}

> **Triangle - Pointing Left**

**&lt;**

**div**

class

=

&quot;triangle-left&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-left

{

**width**

:

0

;

**height**

:

0

;

**border-top**

:

25

px

solid

transparent

;

**border-bottom**

:

25

px

solid

transparent

;

**border-right**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

}

> **Triangle - Pointing Up/Right**

**&lt;**

**div**

class

=

&quot;triangle-up-right&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-up-right

{

**width**

:

0

;

**height**

:

0

;

**border-top**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

**border-left**

:

50

px

solid

transparent

;

}

> **Triangle - Pointing Up/Left**

**&lt;**

**div**

class

=

&quot;triangle-up-left&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-up-left

{

**width**

:

0

;

**height**

:

0

;

**border-top**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

**border-right**

:

50

px

solid

transparent

;

}

> **Triangle - Pointing Down/Right**

**&lt;**

**div**

class

=

&quot;triangle-down-right&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-down-right

{

**width**

:

0

;

**height**

:

0

;

**border-bottom**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

**border-left**

:

50

px

solid

transparent

;

}

> **Triangle - Pointing Down/Left**

**&lt;**

**div**

class

=

&quot;triangle-down-left&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.triangle-down-left

{

**width**

:

0

;

**height**

:

0

;

**border-bottom**

:

50

px

solid

rgb

(

246

,

156

,

85

)

;

**border-right**

:

50

px

solid

transparent

;

}

## Section 38.3: Circles and Ellipses

> **Circle**
>
> To create a **circle**, define an element with an equal width and
> height (a *square*) and then set the border-radius property of this
> element to 50%.

!&lbrack;&rbrack;(./images/image239.jpg){width="1.1458333333333333in"
height="1.1875in"}

<h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;circle&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.circle

{

**width**

:

50

px

;

**height**

:

50

px

;

**background**

:

rgb

(

246

,

156

,

85

)

;

**border-radius**

:

50

&percnt;

;

}

> **Ellipse**
>
> An **ellipse** is similar to a circle, but with different values for
> width and height.

!&lbrack;&rbrack;(./images/image240.jpg){width="0.9375in" height="0.9375in"}

<h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;oval&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.oval

{

**width**

:

50

px

;

**height**

:

80

px

;

**background**

:

rgb

(

246

,

156

,

85

)

;

**border-radius**

:

50

&percnt;

;

}

## Section 38.4: Bursts

> A burst is similar to a star but with the points extending less
> distance from the body. Think of a burst shape as a square with
> additional, slightly rotated, squares layered on top.

  -----------------------------------------------------------------------
  ::before                      and             ::after
  ----------------------------- --------------- -------------------------

  -----------------------------------------------------------------------

> The additional squares are created using the psuedo-elements.
>
> **8 Point Burst**

  -----------------------------------------------------------------------
  before
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> An 8 point burst are 2 layered squares. The bottom square is the
> element itself, the additional square is created using the :
> pseudo-element. The bottom is rotated 20°, the top square is rotated
> 135°.

**&lt;**

**div**

class

=

&quot;burst-8&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.burst-8 {

background: rgb(246, 156, 85);

width: 40px;

height: 40px;

position: relative;

text-align: center;

-ms-transform: rotate(20deg);

transform: rotate(20eg);

}

.burst-8::before {

content: &quot;&quot;;

position: absolute;

top: 0;

left: 0;

height: 40px;

width: 40px;

background: rgb(246, 156, 85);

-ms-transform: rotate(135deg);

transform: rotate(135deg);

}

> **12 Point Burst**

  -----------------------------------------------------------------------
  before                     and :                  after
  -------------------------- ---------------------- ---------------------

  -----------------------------------------------------------------------

> An 12 point burst are 3 layered squares. The bottom square is the
> element itself, the additional squares are created using the :
> pseudo-elements. The bottom is rotated 0°, the next square is rotated
> 30°, and the top is rotated 60°.

**&lt;**

**div**

class

=

&quot;burst-12&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.burst-12 {

width: 40px;

height: 40px;

position: relative;

text-align: center;

background: rgb(246, 156, 85);

}

.burst-12::before, .burst-12::after {

content: &quot;&quot;;

position: absolute;

top: 0;

left: 0;

height: 40px;

width: 40px;

background: rgb(246, 156, 85);

}

.burst-12::before {

-ms-transform: rotate(30deg);

transform: rotate(30deg);

}

.burst-12::after {

-ms-transform: rotate(60deg);

transform: rotate(60deg);

}

## Section 38.5: Square

> To create a square, define an element with both a width and height. In
> the example below, we have an element with a width and height of 100
> pixels each.

**&lt;**

**div**

class

=

&quot;square&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

.square

{

**width**

:

100

px

;

**height**

:

100

px

;

**background**

:

rgb

(

246

,

156

,

85

)

;

}

## Section 38.6: Cube

  -----------------------------------------------------------------------
  skewX                 () and                      skewY
  --------------------- --------------------------- ---------------------

  -----------------------------------------------------------------------

> This example shows how to create a cube using 2D transformation
> methods () on pseudo elements.

!&lbrack;&rbrack;(./images/image244.jpg){width="2.40625in"
height="1.9479166666666667in"}

> **HTML:**

**&lt;**

**div**

class

=

&quot;cube&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> **CSS:**

.cube

{

**background**

:

#dc2e2e

;

**width**

:

100

px

;

**height**

:

100

px

;

**position**

:

relative

;

**margin**

:

50

px

;

}

.cube

::

before

{

**content**

:

&apos;&apos;

;

**display**

:

inline-block

;

**background**

:

#f15757

;

**width**

:

100

px

;

**height**

:

20

px

;

**transform**

:

skewX

(

-40

deg

)

;

**position**

:

absolute

;

**top**

:

-20

px

;

**left**

:

8

px

;

}

.cube

::

after

{

**content**

:

&apos;&apos;

;

**display**

:

inline-block

;

**background**

:

#9e1515

;

**width**

:

16

px

;

**height**

:

100

px

;

**transform**

:

skewY

(

-50

deg

)

;

**position**

:

absolute

;

**top**

:

-10

px

;

**left**

:

100

&percnt;

;

}

&lbrack;**&lbrack;See demo&rbrack;**&rbrack;(https://jsfiddle.net/codename0/9po0r1L1/)

## Section 38.7: Pyramid

  -----------------------------------------------------------------------
  skewY()
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> This example shows how to create a **pyramid** using borders and 2D
> transformation methods and rotate() on pseudo elements.

!&lbrack;&rbrack;(./images/image245.jpg){width="2.1041666666666665in"
height="1.8541666666666667in"}

> **HTML:**

**&lt;**

**div**

class

=

&quot;pyramid&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> **CSS:**

.pyramid

{

**width**

:

100

px

;

**height**

:

200

px

;

**position**

:

relative

;

**margin**

:

50

px

;

}

.pyramid

::

before

,

.pyramid

::

after

{

**content**

:

&apos;&apos;

;

**display**

:

inline-block

;

**width**

:

0

;

**height**

:

0

;

**border**

:

50

px

solid

;

**position**

:

absolute

;

}

.pyramid

::

before

{

**border-color**

:

transparent

transparent

#ff5656

transparent

;

**transform**

:

scaleY

(

2

)

skewY

(

-40

deg

)

rotate

(

45

deg

)

;

}

.pyramid

::

after

{

**border-color**

:

transparent

transparent

#d64444

transparent

;

**transform**

:

scaleY

(

2

)

skewY

(

40

deg

)

rotate

(

-45

deg

)

;

}

# Chapter 39: Columns

## Section 39.1: Simple Example (column-count)

> The CSS multi-column layout makes it easy to create multiple columns
> of text.
>
> **Code**
>
> **&lt;div** id=&quot;multi-columns&quot;**&gt;**Lorem ipsum dolor sit amet,
> consectetur adipisicing elit, sed do eiusmod tempor incididunt ut
> labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
> exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
> Duis aute irure dolor in reprehenderit in voluptate velit esse cillum
> dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
> proident, sunt in culpa qui officia deserunt mollit anim id est
> laborum**&lt;/div&gt;**
>
> .multi-columns {
>
> -moz-column-count: 2; -webkit-column-count: 2; **column-count**: 2; }
>
> **Result**

!&lbrack;&rbrack;(./images/image246.jpg){width="7.48037510936133in"
height="3.572153324584427in"}

## Section 39.2: Column Width

> The column-width property sets the minimum column width. If
> column-count is not defined the browser will make as many columns as
> fit in the available width.
>
> **Code:**
>
> **&lt;div** id=&quot;multi-columns&quot;**&gt;**
>
> Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
> eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
> minim veniam, quis nostrud exercitation ullamco laboris nisi ut
> aliquip ex ea commodo consequat. Duis aute irure dolor in
> reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
> pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
> culpa qui officia deserunt mollit anim id est laborum

**&lt;**

**/div**

**&gt;**

.multi-columns

{

-moz-column-width

:

100

px

;

-webkit-column-width

:

100

px

;

**column-width**

:

100

px

;

}

> **Result**

!&lbrack;&rbrack;(./images/image247.jpg){width="6.125in"
height="3.7083333333333335in"}

# Chapter 40: Multiple columns

> CSS allows to define that element contents wrap into multiple columns
> with gaps and rules between them.

## Section 40.1: Create Multiple Columns

> **&lt;div** class=&quot;content&quot;**&gt;** Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt
> ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim
> veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl
> ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in
> hendrerit in vulputate velit esse molestie consequat, vel illum dolore
> eu feugiat nulla facilisis at vero eros et accumsan et iusto odio
> dignissim qui blandit praesent luptatum zzril delenit augue duis
> dolore te feugait nulla facilisi. Nam liber tempor cum soluta nobis
> eleifend option congue nihil imperdiet doming id quod mazim placerat
> facer possim assum. **&lt;/div&gt;**
>
> CSS

.content

{

&minus;

webkit-column-count

:

3

;

*/&ast; Chrome, Safari, Opera &ast;/*

&minus;

moz-column-count

:

3

;

*/&ast; Firefox &ast;/*

**column-count**

:

3

;

}

## Section 40.2: Basic example

> Consider the following HTML markup:
>
> **&lt;section&gt;** **&lt;p&gt;**Lorem ipsum dolor sit amet, consetetur
> sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et
> dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam
> et justo duo dolores et ea rebum.**&lt;/p&gt;** **&lt;p&gt;** Stet clita kasd
> gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
> Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
> nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat,
> sed diam voluptua. At vero eos et accusam et justo duo dolores et ea
> rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem
> ipsum dolor sit amet.**&lt;/p&gt;** **&lt;p&gt;**Lorem ipsum dolor sit amet,
> consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut
> labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos
> et accusam et justo duo dolores et ea rebum. Stet clita kasd
> gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
> amet.**&lt;/p&gt; &lt;/section&gt;**
>
> With the following CSS applied the content is split into three columns
> separated by a gray column rule of two pixels.

section

{

**columns**

:

3

;

**column-gap**

:

40

px

;

**column-rule**

:

2

px

solid

gray

;

}

See a &lbrack;&lbrack;live sample of this on
JSFiddle&rbrack;&rbrack;(https://jsfiddle.net/vjL9ewmb/).

# Chapter 41: Inline-Block Layout

## Section 41.1: Justified navigation bar

> The horizontally justified navigation (menu) bar has some number of
> items that should be justified. The first (left) item has no left
> margin within the container, the last (right) item has no right margin
> within the container. The distance between items is equal, independent
> on the individual item width.

<h4>HTML</h4>

**&lt;**

**nav**

**&gt;**

**&lt;**

**ul**

**&gt;**

**&lt;**

**li**

**&gt;**

abc

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

abcdefghijkl

**&lt;**

**/li**

**&gt;**

**&lt;**

**li**

**&gt;**

abcdef

**&lt;**

**/li**

**&gt;**

**&lt;**

**/ul**

**&gt;**

**&lt;**

**/nav**

**&gt;**

<h4>CSS</h4>

nav

{

**width**

:

100

&percnt;

;

**line-height**

:

1.4

em

;

}

ul

{

**list-style**

:

none

;

**display**

:

block

;

**width**

:

100

&percnt;

;

**margin**

:

0

;

**padding**

:

0

;

**text-align**

:

justify

;

**margin-bottom**

:

-1.4

em

;

}

ul

:

after

{

**content**

:

&quot;&quot;

;

**display**

:

inline-block

;

**width**

:

100

&percnt;

;

}

li

{

**display**

:

inline-block

;

}

> **Notes**

  -----------------------------------------------------------------------
  after
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> The nav, ul and li tags were chosen for their semantic meaning of &apos;a
> list of navigation (menu) items&apos;. Other tags may also be used of
> course.
>
> The : pseudo-element causes an extra &apos;line&apos; in the ul and thus an
> extra, empty height of this block, pushing other content down. This is
> solved by the negative margin-bottom, which has to have the same
> magnitude as the line-height (but negative).
>
> If the page becomes too narrow for all the items to fit, the items
> will break to a new line (starting from the right) and be justified on
> this line. The total height of the menu will grow as needed.

# Chapter 42: Inheritance

## Section 42.1: Automatic inheritance

> Inheritance the a fundamental mechanism of CSS by which the computed
> values of some properties of an element are applied to its&apos; children.
> This is particularly useful when you want to set a global style to
> your elements rather than having to set said properties to each and
> every element in your markup.
>
> Common properties that are automatically inherited are: font, color,
> text-align, line-height.
>
> Assume the following stylesheet:

#myContainer

{

**color**

:

red

;

**padding**

:

5

px

;

}

  -----------------------------------------------------------------------------------------------------------
  **color**   :   red   not only to the  **&lt;div**   **&gt;** element but also to **&lt;h3**   **&gt;**   **&lt;p**
                                                     the                                   and      
  ----------- --- ----- ---------------- ----------- -------------------------- ---------- -------- ---------

  -----------------------------------------------------------------------------------------------------------

> This will apply **&gt;** elements. However, due to the nature of padding
> its value will ***not*** be inherited to those elements.

**&lt;**

**div**

id

=

&quot;myContainer&quot;

**&gt;**

**&lt;**

**h**

**3**

**&gt;**

Some header

**&lt;**

**/h**

**3**

**&gt;**

**&lt;**

**p**

**&gt;**

Some paragraph

**&lt;**

**/p**

**&gt;**

**&lt;**

**/div**

**&gt;**

## Section 42.2: Enforced inheritance

> Some properties are not automatically inherited from an element down
> to its&apos; children. This is because those properties are typically
> desired to be unique to the element (or selection of elements) to
> which the property is applied to. Common such properties are margin,
> padding, background, display, etc.
>
> However, sometimes inheritance is desired anyway. To achieve this, we
> can apply the inherit value to the property that should be inherited.
> The inherit value can be appied to *any* CSS property and *any* HTML
> element.
>
> Assume the following stylesheet:

#myContainer

{

**color**

:

red

;

**padding**

:

5

px

;

}

#myContainer

p

{

**padding**

:

inherit

;

}

  ------------------------------------------------------------------------------------
  **color**   :   red       to both the              **&lt;h3**   **&gt;** and   **&lt;p**
  ----------- --- --------- ------------------------ ---------- ------------ ---------

  ------------------------------------------------------------------------------------

> This will apply **&gt;** elements due to the inheritance nature of the
> color property.

  -----------------------------------------------------------------------
  **&lt;p**
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> However, the **&gt;** element will also inherit the padding value from
> its&apos; parent because this was specified.

**&lt;**

**div**

id

=

&quot;myContainer&quot;

**&gt;**

**&lt;**

**h**

**3**

**&gt;**

Some header

**&lt;**

**/h**

**3**

**&gt;**

**&lt;**

**p**

**&gt;**

Some paragraph

**&lt;**

**/p**

**&gt;**

**&lt;**

**/div**

**&gt;**

# Chapter 43: CSS Image Sprites

## Section 43.1: A Basic Implementation

> **What&apos;s an image sprite?**
>
> An image sprite is a single asset located within an image sprite
> sheet. An image sprite sheet is an image file that contains more than
> one asset that can be extracted from it.
>
> For example:

!&lbrack;&rbrack;(./images/image248.jpg){width="1.75in" height="1.875in"}

> The image above is an image sprite sheet, and each one of those stars
> is a sprite within the sprite sheet. These sprite sheets are useful
> because they improve performance by reducing the number of HTTP
> requests a browser might have to make.
>
> So how do you implement one? Here&apos;s some example code.
>
<h4>HTML</h4>

**&lt;**

**div**

class

=

&quot;icon icon1&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&quot;icon icon2&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

class

=

&quot;icon icon3&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> <h4>CSS</h4>

.icon

{

**background**

:

url

(

"

icons-sprite.png

"

)

;

**display**

:

inline-block

;

**height**

:

20

px

;

**width**

:

20

px

;

}

.icon1

{

**background-position**

:

0

px

0

px

;

}

.icon2

{

**background-position**

:

-20

px

0

px

;

}

.icon3

{

**background-position**

:

-40

px

0

px

;

}

> By using setting the sprite&apos;s width and height and by using the
> background-position property in CSS (with an x and y value) you can
> easily extract sprites from a sprite sheet using CSS.

<h2 id="ch44">Chapter 44: Clipping and Masking</h2>

| **          | > **Details**                                          |
| Parameter** |                                                        |
|-------------|--------------------------------------------------------|
| clip-source | A URL which can point to an inline SVG element (or) an |
|             | SVG element in an external file that contains the clip |
|             | path&apos;s definition.                                    |

  inset     (),   circle      (),   ellipse       () or     polygon


> Refers to one among (). Using one of these

  basic-shape         functions the clipping path is defined. These shape
                      functions work exactly the same way as they do in Shapes
                      for Floats

  clip-geometry-box   This can have one among content-box, padding-box,

                      border-box, margin-box, fill-box, stroke-box, view-box
                      as values. When this is provided without any value for
                      &lt;basic-shape&gt;, the edges of the corresponding box is
                      used as the path for clipping. When used with a
                      &lt;basic-shape&gt;, this acts as the reference box for the
                      shape.

  mask-reference      This can be none or an image or a reference URL to a
                      mask image source.

  repeat-style        This specifies how the mask should be repeated or tiled
                      in the X and Y axes. The supported values are repeat-x,
                      repeat-y, repeat, space, round, no-repeat.

  mask-mode           Can be alpha or luminance or auto and indicates whether
                      the mask should be treated as a alpha mask or a
                      luminance mask. If no value is provided and the
                      mask-reference is a direct image then it would be
                      considered as alpha mask (or) if the mask-reference is a
                      URL then it would be considered as luminance mask.

  position            This specifies the position of each mask layer and is
                      similar in behavior to the backgroundposition property.
                      The value can be provided in 1 value syntax (like top,
                      10%) or in 2 value

  top right                             ,   50% 50%


> syntax (like ).

  geometry-box   This specifies the box to which the mask should be clipped (*mask
                 painting area*) or the box which should be used as reference for the
                 mask&apos;s origin (*mask positioning area*) depending on the property. The
                 list of possible values are content-box, padding-box, border-box,
                 margin-box, fill-box, stroke-box, view-box. Detailed explanation of how
                 each of those values work is available in the &lbrack;&lbrack;W3C
                 Spec&rbrack;&rbrack;(https://www.w3.org/TR/css-masking/#the-mask-clip).

  bg-size        This represents the size of each mask-image layer and has the same
                 syntax as backgroundsize. The value can be length or percentage or auto
                 or cover or contain. Length, percentage and auto can either be provided
                 as a single value or as one for each axis.

> This can be any one among add, subtract, exclude, multiply per layer
> and defines the type
>
> compositing-operator of compositing operation that should be used for
> this layer with those below it. Detailed explanation about each value
> is available in the &lbrack;&lbrack;W3C
> Specs&rbrack;&rbrack;(https://www.w3.org/TR/css-masking/#the-mask-composite).

<h3 id="ch44-1">Section 44.1: Clipping and Masking: Overview and Dierence</h3>

> With **Clipping** and **Masking** you can make some specified parts of
> elements transparent or opaque. Both can be applied to any HTML
> element.
>
> **Clipping**

  circle          (),     polygon           () or        ellipse


> Clips are vector paths. Outside of this path the element will be
> transparent, inside it&apos;s opaque. Therefore you can define a clip-path
> property on elements. Every graphical element that also exists in SVG
> you can use here as a function to define the path. Examples are ().

!&lbrack;&rbrack;(./images/image249.jpg){width="3.3333333333333335in"
height="2.71875in"}

> Example

**clip-path**

:

circle

(

100

px

at

center

)

;

> The element will be only visible inside of this circle, which is
> positioned at the center of the element and has a radius of 100px.
>
> **Masking**
>
> Masks are similar to Clips, but instead of defining a path you define
> a mask what layers over the element. You can imagine this mask as an
> image what consist of mainly two colors: black and white.
>
> **Luminance Mask**: Black means the region is opaque, and white that
> it&apos;s transparent, but there is also a grey area which is
> semi-transparent, so you are able to make smooth transitions.
>
> **Alpha Mask**: Only on the transparent areas of the mask the element
> will be opaque.

!&lbrack;&rbrack;(./images/image250.jpg){width="3.3333333333333335in"
height="2.0625in"}

> This image for example can be used as a luminance mask to make for an
> element a very smooth transition from right to left and from opaque to
> transparent.
>
> The mask property let you specify the the mask type and an image to be
> used as layer.
>
> Example

**mask**

:

url

(

masks

.svg

#rectangle

)

luminance

;

> An element called rectangle defined in masks.svg will be used as an
> **luminance mask** on the element.

## Section 44.2: Simple mask that fades an image from solid to transparent

> <h4>CSS</h4>

div

{

**height**

:

200

px

;

**width**

:

200

px

;

**background**

:

url

(

http

:

//lorempixel.com/

200

/

200

/nature/

1

)

;

**mask-image**

:

linear-gradient

(

to

right

,

white

,

transparent

)

;

}

<h4>HTML</h4>

```
**&lt;**
**div**
**&gt;**
**&lt;**
**/div**
**&gt;**
```

> In the above example there is an element with an image as its
> background. The mask that is applied on the image (using CSS) makes it
> look as though it is fading out from left to right.
>
> The masking is achieved by using a linear-gradient that goes from
> white (on the left) to transparent (on the right) as the mask. As it
> is an alpha mask, image becomes transparent where the mask is
> transparent.
>
> **Output without the mask:**

[image251.jpg 2.18 x 2.18](./images/image251.jpg)

> **Output with the mask:**

[image252.jpg 2.18 x 2.18](./images/image252.jpg)

> **Note:** As mentioned in remarks, the above example would work in
> Chrome, Safari and Opera only when used with the -webkit prefix. This
> example (with a linear-gradient as mask image) is not yet supported in
> Firefox.

<h3 id="ch44-3">Section 44.3: Clipping (Circle)</h3>

<h4>CSS:</h4>

```
div
{
**width**
:
200
px
;
**height**
:
200
px
;
**background**
:
teal
;
**clip-path**
:
circle
(
30
&percnt;
at
50
&percnt;
50
&percnt;
)
;
*/&ast; refer remarks before usage &ast;/*
}
```

<h4>HTML</h4>

```
**&lt;**
**div**
**&gt;**
**&lt;**
**/div**
**&gt;**
```

> This example shows how to clip a div to a circle. The element is
> clipped into a circle whose radius is 30% based on the dimensions of
> the reference box with its center point at the center of the reference
> box. Here since no &lt;clipgeometry-box&gt; (in other words, reference
> box) is provided, the border-box of the element will be used as the
> reference box.
>
> The circle shape needs to have a radius and a center with (x,y)
> coordinates:

circle

```
(
radius at x y
)
```

&lbrack;**&lbrack;View Example&rbrack;**&rbrack;(https://jsfiddle.net/webtiki/qp69n494/)
**Output:**

[image253.jpg 2.468 x 2.229](./images/image253.jpg)

<h3 id="ch44-4">Section 44.4: Clipping (Polygon)</h3>

<h4>CSS:</h4>

```
div
{
**width**
:
200
px
;
**height**
:
200
px
;
**background**
:
teal
;
**clip-path**
:
polygon
(
0
0
,
0
100
&percnt;
,
100
&percnt;
50
&percnt;
)
;
*/&ast; refer remarks before usage &ast;/*
}
```

<h4>HTML:</h4>

```
**&lt;**
**div**
**&gt;**
**&lt;**
**/div**
**&gt;**
```

> In the above example, a **polygonal** clipping path is used to clip
> the square (200 x 200) element into a triangle shape. The output shape
> is a triangle because the path starts at (that is, first coordinates
> are at) 0 0 - which is the top-left

  100%   &minus; which is bottom-left corner of the box and then       100% 50%
         finally to                                               


> corner of the box, then goes to 0 which is
>
> nothing but the right-middle point of the box. These paths are self
> closing (that is, the starting point will be the ending point) and so
> the final shape is that of a triangle.
>
> This can also be used on an element with an image or a gradient as
> background.

&lbrack;**&lbrack;View Example&rbrack;**&rbrack;(https://jsfiddle.net/eoa4a94k/)

> **Output:**

[image254.jpg 2.16 x 2.16](./images/image254.jpg)

<h3 id="ch44-5">Section 44.5: Using masks to cut a hole in the middle of an image</h3>

> <h4>CSS</h4>

div

{

**width**

:

200

px

;

**height**

:

200

px

;

**background**

:

url

(

http

:

//lorempixel.com/

200

/

200

/abstract/

6

)

;

**mask-image**

:

radial-gradient

(

circle

farthest-side at

center

,

transparent

49

&percnt;

,

white

50

&percnt;

)

;

*/&ast; check*

*remarks before using &ast;/*

}

<h4>HTML</h4>
>
> In the above example, a transparent circle is created at the center
> using radial-gradient and this is then used as a mask to produce the
> effect of a circle being cut out from the center of an image.
>
> **Image without mask:**

[image255.jpg 2.16 x 2.16](./images/image255.jpg)

> **Image with mask:**

[image256.jpg 2.16 x 2.16](./images/image256.jpg)

<h3 id="ch44-6">Section 44.6: Using masks to create images with irregular shapes</h3>

> <h4>CSS</h4>

div

{

*/&ast; check remarks before usage &ast;/*

**height**

:

200

px

;

**width**

:

400

px

;

**background-image**

:

url

(

http

:

//lorempixel.com/

400

/

200

/nature/

4

)

;

**mask-image**

:

linear-gradient

(

to

top

right

,

transparent

49.5

&percnt;

,

white

50.5

&percnt;

)

,

linear-gradient

(

to

top

left

,

transparent

49.5

&percnt;

,

white

50.5

&percnt;

)

,

linear-gradient

(

white

,

white

)

;

**mask-size**

:

75

&percnt;

25

&percnt;

,

25

&percnt;

25

&percnt;

,

100

&percnt;

75

&percnt;

;

**mask-position**

:

bottom

left

,

bottom

right

,

top

left

;

**mask-repeat**

:

no-repeat

;

}

> <h4>HTML</h4>

**&lt;**

**div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> In the above example, three linear-gradient images (which when placed
> in their appropriate positions would cover 100% x 100% of the
> container&apos;s size) are used as masks to produce a transparent
> triangular shaped cut at the bottom of the image.
>
> **Image without the mask:**

[image257.jpg 4.25 x 2.167](./images/image257.jpg)

> **Image with the mask:**

[image258.jpg 4.26 x 2.21](./images/image258.jpg)

<h2 id="ch45">Chapter 45: Fragmentation</h2>

**Value Description**

> auto Default. Automatic page breaks always Always insert a page break
> avoid Avoid page break (if possible) left Insert page breaks so that
> the next page is formatted as a left page right Insert page breaks so
> that the next page is formatted as a right page initial Sets this
> property to its default value. inherit Inherits this property from its
> parent element.

## Section 45.1: Media print page-break

**&commat;media**

print

{

p

{

**page-break-inside**

:

avoid

;

}

h1

{

**page-break-before**

:

always

;

}

h2

{

**page-break-after**

:

avoid

;

}

}

> This code does 3 things:
>
> it prevents a page break inside any p tags, meaning a paragraph will
> never be broken in two pages, if possible.
>
> it forces a page-break-before in all h1 headings, meaning that before
> every h1 occurrence, there will be a page break.
>
> it prevents page-breaks right after any h2

# Chapter 46: CSS Object Model (CSSOM)

## Section 46.1: Adding a background-image rule via the CSSOM

> To add a background-image rule via the CSSOM, first get a reference to
> the rules of the first stylesheet:

var

stylesheet

=

document.styleSheets

&lbrack;

0

&rbrack;

.cssRules

;

> Then, get a reference to the end of the stylesheet:

var

end

=

stylesheet

.length

&minus;

1

;

> Finally, insert a background-image rule for the body element at the
> end of the stylesheet:
>
> stylesheet.insertRule(&quot;body { background-image:
> url(&apos;http://cdn.sstatic.net/Sites/stackoverflow/img/favicon.ico&apos;);
> }&quot;, end);

## Section 46.2: Introduction

> The browser identifies tokens from stylesheet and coverts them into
> nodes which are linked into a tree structure. The entire map of all
> the nodes with their associated styles of a page would be the CSS
> Object Model.
>
> To display the webpage, a web browser takes following steps.

1.  The web browser examines your HTML and builds the DOM (Document
    Object Model).

2.  The web browser examines your CSS and builds the CSSOM (CSS Object
    Model).

3.  The web browser combines the DOM and the CSSOM to create a render
    tree. The web browser displays your webpage.

[image259.jpg 7.5 x 3](./images/image259.jpg)

<h2 id="ch47">Chapter 47: Feature Queries</h2>

**Parameter Details**

  property                              :    value

> Evaluates true if the browser can handle the CSS rule. The parenthesis
> around the rule are
>
> ()
>
> required.
>
> and Returns true only if both the previous and next conditions are
> true. not Negates the next condition or Returns true if either the
> previous or next condition is true.

  -----------------------------------------------------------------------
  &period;..
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

() Groups conditions

## Section 47.1: Basic &commat;supports usage

**&commat;supports**

(

**display**

:

flex

)

{

*/&ast; Flexbox is available, so use it &ast;/*

.my-container

{

**display**

:

flex

;

}

}

> In terms of syntax, &commat;supports is very similar to &commat;media, but instead
> of detecting screen size and orientation, &commat;supports will detect
> whether the browser can handle a given CSS rule.

  --------------------------------------------------------------------------------------------------
  **&commat;supports**   (   flex   ), notice that the rule  **&commat;supports**   (   **display**   :   flex
                              is                                                              
  ---------------- --- ------ ------------------------ ---------------- --- ------------- --- ------

  --------------------------------------------------------------------------------------------------

Rather than doing something like ).

## Section 47.2: Chaining feature detections

> To detect multiple features at once, use the and operator.

**&commat;supports**

(

**transform**

:

translateZ

(

1

px

)

)

and

(

**transform-style**

:

preserve-3d

)

and

(

**perspective**

:

1

px

)

{

*/&ast; Probably do some fancy 3d stuff here &ast;/*

}

There is also an

or

operator and a

not

operator:

**&commat;supports**

(

**display**

:

flex

)

or

(

**display**

:

table-cell

)

{

*/&ast; Will be used if the browser supports flexbox or display: table-cell
&ast;/*

}

**&commat;supports**

not

(

webkit-transform

&minus;

:

translate

(

0

,

0

,

0

)

)

{

*/&ast; Will &ast;not&ast; be used if the browser supports -webkit-transform:
translate(&period;..) &ast;/*

}

> For the ultimate &commat;supports experience, try grouping logical
> expressions with parenthesis:

**&commat;supports**

(

(

**display**

:

block

)

and

(

zoom

:

1

)

)

or

(

(

**display**

:

flex

)

and

(

not

(

**display**

:

table-cell

)

)

)

or

(

**transform**

:

translateX

(

1

px

)

)

{

*/&ast; &period;.. &ast;/*

}

> This will work if the browser

  -------------------------------------------------------------------------
  **display**           :   block              AND             zoom
  --------------------- --- ------------------ --------------- ------------

  -------------------------------------------------------------------------

1.  Supports : 1, or

  -------------------------------------------------------------------------------
  **display**   :   flex     AND NOT         **display**   :   table-cell
  ------------- --- -------- --------------- ------------- --- ------------------

  -------------------------------------------------------------------------------

2.  Supports , or

  --------------------------------------------------------------------------
  **transform**             :   translateX                      (   1px
  ------------------------- --- ------------------------------- --- --------

  --------------------------------------------------------------------------

3.  Supports ).

# Chapter 48: Stacking Context

## Section 48.1: Stacking Context

> In this example every positioned element creates its own stacking
> context, because of their positioning and z-index values. The
> hierarchy of stacking contexts is organized as follows:

Root

DIV #1

DIV #2

DIV #3

DIV #4

DIV #5

DIV #6

> It is important to note that DIV #4, DIV #5 and DIV #6 are children of
> DIV #3, so stacking of those elements is completely resolved within
> DIV#3. Once stacking and rendering within DIV #3 is completed, the
> whole DIV #3 element is passed for stacking in the root element with
> respect to its sibling&apos;s DIV.
>
> **HTML:**

**&lt;**

**div**

id

=

&quot;div1&quot;

**&gt;**

**&lt;**

**h**

**1**

**&gt;**

Division Element #1

**&lt;**

**/h**

**1**

**&gt;**

**&lt;**

**code**

**&gt;**

position: relative;

**&lt;**

**br**

**/&gt;**

z-index: 5;

**&lt;**

**/code**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

id

=

&quot;div2&quot;

**&gt;**

**&lt;**

**h**

**1**

**&gt;**

Division Element #2

**&lt;**

**/h**

**1**

**&gt;**

**&lt;**

**code**

**&gt;**

position: relative;

**&lt;**

**br**

**/&gt;**

z-index: 2;

**&lt;**

**/code**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

id

=

&quot;div3&quot;

**&gt;**

**&lt;**

**div**

id

=

&quot;div4&quot;

**&gt;**

**&lt;**

**h**

**1**

**&gt;**

Division Element #4

**&lt;**

**/h**

**1**

**&gt;**

**&lt;**

**code**

**&gt;**

position: relative;

**&lt;**

**br**

**/&gt;**

z-index: 6;

**&lt;**

**/code**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**h**

**1**

**&gt;**

Division Element #3

**&lt;**

**/h**

**1**

**&gt;**

**&lt;**

**code**

**&gt;**

position: absolute;

**&lt;**

**br**

**/&gt;**

z-index: 4;

**&lt;**

**/code**

**&gt;**

**&lt;**

**div**

id

=

&quot;div5&quot;

**&gt;**

**&lt;**

**h**

**1**

**&gt;**

Division Element #5

**&lt;**

**/h**

**1**

**&gt;**

**&lt;**

**code**

**&gt;**

position: relative;

**&lt;**

**br**

**/&gt;**

z-index: 1;

**&lt;**

**/code**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**div**

id

=

&quot;div6&quot;

**&gt;**

**&lt;**

**h**

**1**

**&gt;**

Division Element #6

**&lt;**

**/h**

**1**

**&gt;**

**&lt;**

**code**

**&gt;**

position: absolute;

**&lt;**

**br**

**/&gt;**

z-index: 3;

**&lt;**

**/code**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> **CSS:**

#div5

{

**border**

:

1

px

dashed

#996

;

**background-color**

:

#ffc

;

}

#div4

{

**z-index**

:

6

;

**margin-bottom**

:

15

px

;

**padding**

:

25

px

10

px

5

px

;

}

#div5

{

**z-index**

:

1

;

**margin-top**

:

15

px

;

**padding**

:

5

px

10

px

;

}

#div6

{

**z-index**

:

3

;

**position**

:

absolute

;

**top**

:

20

px

;

**left**

:

180

px

;

**width**

:

150

px

;

**height**

:

125

px

;

**border**

:

1

px

dashed

#009

;

**padding-top**

:

125

px

;

**background-color**

:

#ddf

;

**text-align**

:

center

;

}

> **Result:**

[image260.jpg 6x3 inc](./images/image260.jpg)

> Source:

&lbrack;&lbrack;https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context).

# Chapter 49: Block Formatting Contexts

## Section 49.1: Using the overflow property with a value dierent to visible

img

{

**float**

:

left

;

**width**

:

100

px

;

**margin**

:

0

10

px

;

}

.div1

{

**background**

:

#f1f1f1

;

*/&ast; does not create block formatting context &ast;/*

}

.div2

{

**background**

:

#f1f1f1

;

**overflow**

:

hidden

;

*/&ast; creates block formatting context &ast;/*

}

[image261.jpg 6 x 3](./images/image261.jpg)

&lbrack;&lbrack;https://jsfiddle.net/MadalinaTn/qkwwmu6m/2/&rbrack;&rbrack;(https://jsfiddle.net/MadalinaTn/qkwwmu6m/2/)

> &lbrack;&lbrack;Using the overflow property with a value different to visible (its
> default) will create a new block formatting&rbrack; &lbrack;context.
> This is technically necessary&rbrack; &lbrack;---&rbrack; &lbrack;if a
> float intersected with the scrolling element it would
> forcibly&rbrack; &lbrack;rewrap the
> content.&rbrack;&rbrack;(https://css-tricks.com/almanac/properties/o/overflow/)
>
> This example that show how a number of paragraphs will interact with a
> floated image is similar to &lbrack;&lbrack;this
> example&rbrack;&rbrack;(https://css-tricks.com/almanac/properties/o/overflow/),
> on css-tricks.com.

&lbrack;&lbrack;2&rbrack;&rbrack;(https://css-tricks.com/almanac/properties/o/overflow/):
&lbrack;&lbrack;https://developer.mozilla.org/en-US/docs/Web/CSS/overflow&rbrack;&rbrack;(https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
MDN

# Chapter 50: Vertical Centering

## Section 50.1: Centering with display: table

> **HTML:**

**&lt;**

**div**

class

=

&quot;wrapper&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;outer&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;inner&quot;

**&gt;**

centered

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> **CSS:**

.wrapper

{

**height**

:

600

px

;

**text-align**

:

center

;

}

.outer

{

**display**

:

table

;

**height**

:

100

&percnt;

;

**width**

:

100

&percnt;

;

}

.outer

.inner

{

**display**

:

table-cell

;

**text-align**

:

center

;

**vertical-align**

:

middle

;

}

## Section 50.2: Centering with Flexbox

> **HTML:**

**&lt;**

**div**

class

=

&quot;container&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;child&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> **CSS:**

.container

{

**height**

:

500

px

;

**width**

:

500

px

;

**display**

:

flex

;

// Use Flexbox

**align-items**

:

center

;

// This centers children vertically in the parent.

**justify-content**

:

center

;

// This centers children horizontally.

**background**

:

white

;

}

.child

{

**width**

:

100

px

;

**height**

:

100

px

;

**background**

:

blue

;

}

## Section 50.3: Centering with Transform

> **HTML:**

**&lt;**

**div**

class

=

&quot;wrapper&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;centered&quot;

**&gt;**

centered

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> **CSS:**

.wrapper

{

**position**

:

relative

;

**height**

:

600

px

;

}

.centered

{

**position**

:

absolute

;

**z-index**

:

999

;

**transform**

:

translate

(

-50

&percnt;

,

-50

&percnt;

)

;

**top**

:

50

&percnt;

;

**left**

:

50

&percnt;

;

}

## Section 50.4: Centering Text with Line Height

> **HTML:**

**&lt;**

**div**

class

=

&quot;container&quot;

**&gt;**

**&lt;**

**span**

**&gt;**

vertically centered

**&lt;**

**/span**

**&gt;**

**&lt;**

**/div**

**&gt;**

> **CSS:**

.container

{

**height**

:

50

px

;

*/&ast; set height &ast;/*

**line-height**

:

50

px

;

*/&ast; set line-height equal to the height &ast;/*

**vertical-align**

:

middle

;

*/&ast; works without this rule, but it is good having it explicitly set
&ast;/*

}

> **Note:** This method will only vertically center a *single line of
> text*. It will not center block elements correctly and if the text
> breaks onto a new line, you will have two very tall lines of text.

## Section 50.5: Centering with Position: absolute

> **HTML:**

**&lt;**

**div**

class

=

&quot;wrapper&quot;

**&gt;**

**&lt;**

**img**

src

=

&quot;http://cdn.sstatic.net/Sites/stackoverflow/company/img/logos/so/so-icon.png?v=c78bd457575a&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

> **CSS:**

.wrapper

{

**position**

:

relative

;

**height**

:

600

px

;

}

.wrapper

img

{

**position**

:

absolute

;

**top**

:

0

;

**left**

:

0

;

**right**

:

0

;

**bottom**

:

0

;

**margin**

:

auto

;

}

> If you want to center other then images, then you must give height and
> width to that element.
>
> **HTML:**

**&lt;**

**div**

class

=

&quot;wrapper&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;child&quot;

**&gt;**

make me center

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> **CSS:**

.wrapper

{

**position**

:

relative

;

**height**

:

600

px

;

}

.wrapper

.child

{

**position**

:

absolute

;

**top**

:

0

;

**left**

:

0

;

**right**

:

0

;

**bottom**

:

0

;

**margin**

:

auto

;

**width**

:

200

px

;

**height**

:

30

px

;

**border**

:

1

px

solid

#f00

;

}

## Section 50.6: Centering with pseudo element

> **HTML:**

**&lt;**

**div**

class

=

&quot;wrapper&quot;

**&gt;**

**&lt;**

**div**

class

=

&quot;content&quot;

**&gt;**

**&lt;**

**/div**

**&gt;**

**&lt;**

**/div**

**&gt;**

> **CSS:**

.wrapper

{

**min-height**

:

600

px

;

}

.wrapper

:

before

{

**content**

:

&quot;&quot;

;

**display**

:

inline-block

;

**height**

:

100

&percnt;

;

**vertical-align**

:

middle

;

}

.content

{

**display**

:

inline-block

;

**height**

:

80

px

;

**vertical-align**

:

middle

;

}

> This method is best used in cases where you have a varied-height
> .content centered inside .wrapper; and you want .wrapper&apos;s height to
> expand when .content&apos;s height exceed .wrapper&apos;s min-height.

# Chapter 51: Object Fit and Placement

## Section 51.1: object-fit

> The **object-fit** property will defines how an element will fit into
> a box with an established height and width. Usually applied to an
> image or video, Object-fit accepts the following five values:
>
> **FILL**

**object-fit**

:

fill

;

> Fill stretches the image to fit the content box without regard to the
> image&apos;s original aspect ratio.
>
> **CONTAIN**

**object-fit**

:

contain

;

> Contain fits the image in the box&apos;s height or width while maintaining
> the image&apos;s aspect ratio.
>
> **COVER**

**object-fit**

:

cover

;

[image264.jpg 6.2 x 2.8](./images/image264.jpg)

> Cover fills the entire box with the image. The image aspect ratio is
> preserved, but the image is cropped to the dimensions of the box.
>
> **NONE**

**object-fit**

:

none

;

> None ignores the size of the box and is not resized.
>
> **SCALE-DOWN**

**object-fit**

:

scale-down

;

> Scale-down either sizes the object as none or as contain. It displays
> whichever option results in a smaller image size.

[image266.jpg 7.2 x 3.65](./images/image266.jpg)

<h2 id="ch52">Chapter 52: CSS design patterns</h2>

> These examples are for documenting CSS-specific design patterns like
> &lbrack;&lbrack;BEM&rbrack;&rbrack;(http://getbem.com/),
> &lbrack;&lbrack;OOCSS&rbrack;&rbrack;(https://www.smashingmagazine.com/2011/12/an-introduction-to-object-oriented-css-oocss/)
> and &lbrack;&lbrack;SMACSS&rbrack;&rbrack;(https://smacss.com/).
>
> These examples are NOT for documenting CSS frameworks like
> &lbrack;&lbrack;Bootstrap&rbrack;&rbrack;(http://getbootstrap.com/) or
> &lbrack;&lbrack;Foundation&rbrack;&rbrack;(http://foundation.zurb.com/).

<h3 id="ch52-1">Section 52.1: BEM</h3>

  -------------------------------------------------------------------------
  Blocks         ,   Elements and Modifiers
  -------------- --- ------------------------------------------------------

  -------------------------------------------------------------------------

> &lbrack;&lbrack;BEM&rbrack;&rbrack;(http://getbem.com/introduction/) stands for .
> It&apos;s a methodology initially conceived by Russian tech company
>
> &lbrack;&lbrack;Yandex&rbrack;&rbrack;(https://en.wikipedia.org/wiki/Yandex), but
> which gained quite some traction among American & Western-European web
> developers as well.
>
> As the same implies, BEM metholology is all about componentization of
> your HTML and CSS code into three types of components:
>
> **Blocks:** standalone entities that are meaningful on their own
>
> Examples are header, container, menu, checkbox & textbox
>
> **Elements:** Part of blocks that have no standalone meaning and are
> semantically tied to their blocks.

  -----------------------------------------------------------------------
  menu item         , list item,          checkbox caption
  ----------------- --------------------- -------------------------------

  -----------------------------------------------------------------------

> Examples are & header title
>
> **Modifiers:** Flags on a block or element, used to change appearance
> or behavior

  -----------------------------------------------------------------------
  color yellow
  -----------------------------------------------------------------------

  -----------------------------------------------------------------------

> Examples are disabled, highlighted, checked, fixed, size big &
>
> The goal of BEM is to keep optimize the readability, maintainability
> and flexibility of your CSS code. The way to achieve this, is to apply
> the following rules.

  -----------------------------------------------------------------------
  blockname&minus;-modifiername        and   blockname&lowbar;&lowbar;elementname&minus;-
  ------------------------------- ----- ---------------------------------

  -----------------------------------------------------------------------

> Block styles are never dependent on other elements on a page
>
> Blocks should have a simple, short name and avoid &lowbar; or - characters
>
> When styling elements, use selectors of format
> blockname&lowbar;&lowbar;elementname When styling modifiers, use selectors of
> format modifiername
>
> Elements or blocks that have modifiers should inherit everything from
> the block or element it is modifying except the properties the
> modifier is supposed to modify
>
> **Code example**
>
> If you apply BEM to your form elements, your CSS selectors should look
> something like this:
>
> .form { } // Block
>
> .form&minus;-theme-xmas { } // Block + modifier .form&minus;-simple { } //
> Block + modifier
>
> .form&lowbar;&lowbar;input { } // Block &gt; element
>
> .form&lowbar;&lowbar;submit { } // Block &gt; element
>
> .form&lowbar;&lowbar;submit&minus;-disabled { } // Block &gt; element + modifier
>
> The corresponding HTML should look something like this:

**&lt;**

**form**

class

=

&quot;form form&minus;-theme-xmas form&minus;-simple&quot;

**&gt;**

**&lt;**

**input**

class

=

&quot;form&lowbar;&lowbar;input&quot;

type

=

&quot;text&quot;

**/&gt;**

**&lt;**

**input**

class

=

&quot;form&lowbar;&lowbar;submit form&lowbar;&lowbar;submit&minus;-disabled&quot;

type

=

&quot;submit&quot;

**/&gt;**

**&lt;**

**/form**

**&gt;**

# Chapter 53: Browser Support & Prefixes

**Prefix Browser(s)**

> -webkit- Google Chrome, Safari, newer versions of Opera 12 and up,
> Android, Blackberry and UC browsers -moz- Mozilla Firefox

-ms- Internet Explorer, Edge

  -----------------------------------------------------------------------
  -o-                                 
  ----------------------------------- -----------------------------------
  , -xv-                              

  -----------------------------------------------------------------------

> Opera until version 12
>
> -khtml- Konquerer

## Section 53.1: Transitions

div

{

-webkit-transition

:

all

4

s

ease

;

-moz-transition

:

all

4

s

ease

;

-o-transition

:

all

4

s

ease

;

**transition**

:

all

4

s

ease

;

}

## Section 53.2: Transform

div

{

-webkit-transform

:

rotate

(

45

deg

)

;

-moz-transform

:

rotate

(

45

deg

)

;

-ms-transform

:

rotate

(

45

deg

)

;

-o-transform

:

rotate

(

45

deg

)

;

**transform**

:

rotate

(

45

deg

)

;

}

# Chapter 54: Normalizing Browser Styles

> Every browser has a default set of CSS styles that it uses for
> rendering elements. These default styles may not be consistent across
> browsers because: the language specifications are unclear so base
> styles are up for interpretation, browsers may not follow
> specifications that are given, or browsers may not have default styles
> for newer HTML elements. As a result, people may want to normalize
> default styles across as many browsers as possible.

## Section 54.1: normalize.css

> Browsers have a default set of CSS styles they use for rendering
> elements. Some of these styles can even be customised using the
> browser&apos;s settings to change default font face and size definitions,
> for example. The styles contain the definition of which elements are
> supposed to be block-level or inline, among other things.
>
> Because these default styles are given some leeway by the language
> specifications and because browsers may not follow the specs properly
> they can differ from browser to browser.
>
> This is where
> &lbrack;&lbrack;normalize.css&rbrack;&rbrack;(http://necolas.github.io/normalize.css/)
> comes into play. It overrides the most common inconsistencies and
> fixes known bugs.
>
> **What does it do**
>
> Preserves useful defaults, unlike many CSS resets.
>
> Normalizes styles for a wide range of elements.
>
> Corrects bugs and common browser inconsistencies.
>
> Improves usability with subtle modifications.
>
> Explains what code does using detailed comments.
>
> So, by including normalize.css in your project your design will look
> more alike and consistent across different browsers.
>
> **Difference to reset.css**
>
> You may have heard of reset.css. What&apos;s the difference between the
> two?
>
> While normalize.css provides consistency by setting different
> properties to unified defaults, reset.css achieves consistency by
> **removing** all basic styling that a browser may apply. While this
> might sound like a good idea at first, this actually means you have to
> write **all** rules yourself, which goes against having a solid
> standard.

## Section 54.2: Approaches and Examples

> CSS resets take separate approaches to browser defaults. Eric Meyer's
> Reset CSS has been around for a while. His approach nullifies many of
> the browser elements that have been known to cause problems right off
> the back. The following is from his version (v2.0 &vertbar; 20110126) CSS
> Reset.

html, body, div, span, applet, object, iframe,

h1, h2, h3, h4, h5, h6,

**p**

, blockquote, pre,

a, abbr, acronym, address, big, cite, code,

del, dfn, em, img, ins, kbd, q, s, samp,

small, strike, strong,

**sub**

, sup, tt, var,

b, u, i, center,

dl, dt, dd, ol, ul, li,

fieldset, form, label, legend,

table, caption, tbody, tfoot, thead, tr, th, td,

article, aside, canvas, details, embed,

figure, figcaption, footer, header, hgroup,

menu, nav, output, ruby, section, summary,

time, mark, audio, video

**{**

margin:

0

;

padding:

0

;

border:

0

;

font

**-**

size:

100

**%**

;

font: inherit;

vertical

**-**

align: baseline;

**}**

&lbrack;&lbrack;Eric Meyer&apos;s Reset
CSS&rbrack;&rbrack;(http://meyerweb.com/eric/tools/css/reset/)

> Normalize CSS on the other and deals with many of these separately.
> The following is a sample from the version (v4.2.0) of the code.

*/&ast;&ast;*

*&ast; 1. Change the default font family in all browsers (opinionated).*

*&ast; 2. Correct the line height in all browsers.*

*&ast; 3. Prevent adjustments of font size after orientation changes in IE
and iOS.*

*&ast;/*

*/&ast; Document*

*==========================================================================
&ast;/*

html

{

**font-family**

:

sans-serif

;

*/&ast; 1 &ast;/*

**line-height**

:

1.15

;

*/&ast; 2 &ast;/*

-ms-text-size-adjust

:

100

&percnt;

;

*/&ast; 3 &ast;/*

-webkit-text-size-adjust

:

100

&percnt;

;

*/&ast; 3 &ast;/*

}

*/&ast; Sections*

*==========================================================================
&ast;/*

*/&ast;&ast;*

*&ast; Remove the margin in all browsers (opinionated).*

*&ast;/*

body

{

**margin**

:

0

;

}

*/&ast;&ast;*

*&ast; Add the correct display in IE 9-.*

*&ast;/*

article

,

aside

,

footer

,

header

,

nav

,

section

{

**display**

:

block

;

}

*/&ast;&ast;*

*&ast; Correct the font size and margin on &apos;h1&apos; elements within
&apos;section&apos; and*

*&ast; &apos;article&apos; contexts in Chrome, Firefox, and Safari.*

*&ast;/*

h1

{

**font-size**

:

2

em

;

**margin**

:

0.67

em

0

;

}

<a href="http://normalize.css/">Normalize CSS</a>

# Chapter 55: Internet Explorer Hacks

## Section 55.1: Adding Inline Block support to IE6 and IE7

**display**

:

inline-block

;

> The display property with the value of inline-block is not supported
> by Internet Explorer 6 and 7. A work-around for this is:

zoom

:

1

;

&ast;

**display**

:

inline

;

  display


> The zoom property triggers the hasLayout feature of elements, and it
> is available only in Internet Explorer. The &ast; makes sure that the
> invalid property executes only on the affected browsers. Other
> browsers will simply ignore the rule.

<h3 id="ch55-2">Section 55.2: High Contrast Mode in Internet Explorer 10 and greater</h3>

> In Internet Explorer 10+ and Edge, Microsoft provides the
> -ms-high-contrast media selector to expose the &quot;High Contrast&quot;
> setting from the browser, which allows the programmer to adjust their
> site&apos;s styles accordingly.
>
> The -ms-high-contrast selector has 3 states: active, black-on-white,
> and white-on-black. In IE10+ it also had a none state, but that is no
> longer supported in Edge going forward.
>
> **Examples**

**&commat;media**

screen and

(

&minus;

ms-high-contrast

:

active

)

,

(

&minus;

ms-high-contrast

:

black-on-white

)

{

.header

{

**background**

:

#fff

;

**color**

:

#000

;

}

}

> This will change the header background to white and the text color to
> black when high contrast mode is active *and* it is in black-on-white
> mode.

<b>&commat;media</b>

screen and

(

&minus;

ms-high-contrast

:

white-on-black

)

{

.header

{

<b>background</b>

:

#000

;

<b>color</b>

:

#fff

;

}

}

> Similar to the first example, but this specifically selects the
> white-on-black state only, and inverts the header colors to a black
> background with white text.
>
> <b>More Information:</b>

<a href="https://msdn.microsoft.com/en-us/library/windows/apps/hh465764.aspx">Microsoft Documentation</a>
on -ms-high-contrast

<h3 id="ch55-3">Section 55.3: Internet Explorer 6 & Internet Explorer 7 only</h3>

> To target Internet Explorer 6 and Internet Explorer 7, start your
> properties with &ast;:

```
.hide-on-ie6-and-ie7 {
&ast;
<b>display</b>: none;
// This line is processed only on IE6 and IE7
}
```

> To target Internet Explorer 8, wrap your selectors inside :

```
<b>&commat;media</b>
&bsol;&bsol; 0
screen {
  .hide-on-ie8 {
    <b>display</b>: none;
  }
}
```

| <b>&commat;media</b> &bsol;&bsol;0             | > screen { }                           |

> Everything between is processed only by I

<h2 id="ch56">Chapter 56: Performance</h2>

<h3 id="ch56-1">Section 56.1: Use transform and opacity to avoid trigger layout</h3>

Changing some CSS attribute will trigger the browser to synchronously
calculate the style and layout, which is a bad thing when you need to
animate at 60fps.

<b>DON&apos;T</b>

Animate with left and top trigger layout.

```
#box {
  <b>left</b>: 0;
  <b>top</b>: 0;
  <b>transition</b>: left 0.5s, top 0.5s;
  <b>position</b>: absolute;
  <b>width</b>: 50px;
  <b>height</b>: 50px;
  <b>background-color</b>: gray;
}
#box.active {
  <b>left</b>: 100px;
  <b>top</b>: 100px;
}
```

<a href="https://jsfiddle.net/trungdq88/gmpzxLyq/">Demo</a>
took 11.7ms for rendering 9.8ms
for painting
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 267.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image267.jpg"
  style="width:100%"
  title=""
  alt="." />
</p>
<!-- [image267.jpg 7.5 x 7.5](./images/image267.jpg) -->

> <b>DO</b>

Animate with transform with the same animation.

```
#box {
  <b>left</b>: 0;
  <b>top</b>: 0;
  <b>position</b>: absolute;
  <b>width</b>: 50px;
  <b>height</b>: 50px;
  <b>background-color</b>: gray;
  <b>transition</b>: transform 0.5s;
  <b>transform</b>: translate3d(0, 0, 0);
}

#box.active {
  <b>transform</b>: translate3d(100px, 100px, 0);
}
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 268.  (xxx) ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p align="center" width="100%">
<img src="./images/image268.jpg"
  style="width:50%"
  title=""
  alt="." />
</p>

<a href="https://jsfiddle.net/trungdq88/Logdo0rn/">jsFiddle Demo</a>
same animation, took <b>1.3ms</b> for rendering, <b>2.0ms</b> for painting.

<!-- [imge268.jpg](./images/image268.jpg) -->
<!-- width 6.2" -->

<!-- the end -->
<!-- 6/28/2024 Fri 5:41pm -->
<!-- 7/1/2024 Mon 2:24am -->
