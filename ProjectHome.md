# Automated Web/HTTP Profiler with Selenium and Python #

by Corey Goldberg (c) 2009, 2011


---


### What is it? ###

Selenium-profiler is a web/http profiler built with Selenium-RC and Python.  It profiles page load time and network traffic for a web page.  The profiler uses Selenium-RC to automate site navigation (via browser), proxy traffic, and sniff the proxy for network traffic stats as requests pass through during a page load.

It is useful to answer questions like:
  * how many http requests does that page make?
  * how fast are the http responses coming back?
  * which http status codes are returned?
  * how many of each object type are requested?
  * what is the total page load time?



---


### License: ###

GNU GPL v3<br>
This program is Free Open Source software<br>
<br>
<hr />

<h3>Contents:</h3>

<ul><li><a href='http://code.google.com/p/selenium-profiler/source/browse/trunk/web_profiler.py'>web_profiler.py</a></li></ul>

<hr />

<h3>How do you use it?</h3>

<ol><li>Install Python<br>
</li><li>Install Java<br>
</li><li>Install Selenium bindings for Python<br>
</li><li>Run Selenium server: 'java -jar selenium-server.jar'<br>
</li><li>Run web_profiler.py</li></ol>

<i><code>*</code>notes:</i><br>
<i>you may need to adjust browser security settings to get it to work properly</i><br>
<i>to run against an HTTPS/SSL enabled site, you need to install a fake certificate.  look inside selenium-server.jar for the cert.</i>

<hr />

<h3>Command Line Parameters:</h3>

<code>web_profiler.py &lt;url&gt; [browser_launcher]</code><br>
<br>
Sample usage:<br>
<br>
<code>$ python web_profiler.py www.google.com</code><br>
<code>$ python web_profiler.py http://www.google.com *firefox</code><br>
<br>

<i>(use <code>*</code>firefox to launch Mozilla Firefox)</i><br>
<i>(use <code>*</code>iexplore or <code>*</code>iexploreproxy to launch Internet Explorer)</i><br>
<i>(use <code>*</code>googlechrome to launch Google Chrome)</i>

<hr />



<h3>Sample Output:</h3>
<code>--------------------------------</code><br>
<code>results for http://www.google.com/</code><br>

<code>content size: 31.096 kb</code><br>

<code>http requests: 7</code><br>
<code>status 200: 6</code><br>
<code>status 204: 1</code><br>

<code>profiler timing:</code><br>
<code>0.344 secs (page load)</code><br>
<code>0.328 secs (network: end last request)</code><br>
<code>0.110 secs (network: end first request)</code><br>

<code>file extensions: (count, size)</code><br>
<code>gif: 1, 3.011 kb</code><br>
<code>ico: 1, 1.150 kb</code><br>
<code>js: 2, 18.083 kb</code><br>
<code>png: 1, 5.401 kb</code><br>
<code>unknown: 2, 3.451 kb</code><br>

<code>http timing detail: (status, method, doc, size, time)</code><br>
<code>204, GET, /generate_204, 0, 62 ms</code><br>
<code>200, GET, /favicon.ico, 1150, 31 ms</code><br>
<code>200, GET, /barcode09.gif, 3011, 31 ms</code><br>
<code>200, GET, /, 3451, 110 ms</code><br>
<code>200, GET, /2cca7b2e99206b9c.js, 3451, 78 ms</code><br>
<code>200, GET, /nav_logo7.png, 5401, 16 ms</code><br>
<code>200, GET, /f_wkquEsVv8.js, 14632, 47 ms</code><br>
<code>--------------------------------</code><br>


<hr />