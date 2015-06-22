# XyJax
 -- Xy-pic extension for MathJax --

----
XyJax is an almost Xy-pic compatible extension for MathJax.

This extension enables you to draw various graphs and diagrams.

See http://sonoisa.github.io/xyjax/xyjax.html for more details. And origins

- MathJax: http://www.mathjax.org/
- Xy-pic: http://www.tug.org/applications/Xy-pic/

This software is under development, so this release is beta-quality.


## Installation instructions

### Installation Method 1. Installing only XyJax on your own server, and using it with the MathJax CDN.

1. Choose the installation location of the XyJax on your own server (referred to as [XyJax loc]).

     e.g. http://sonoisa.github.io/xyjax_ext/
 
 In this case, [XyJax loc] = http://sonoisa.github.io/xyjax_ext .

2. Download XyJax source code.
 - Go to the XyJax download site (this page).
 - Click the Download Zip button.
 - Extract the downloaded file to a directory (referred to as [XyJax dir]). e.g.

   >     $ unzip  sonoisa-XyJax-xxxxx -d ~/work
   
 In this case, [XyJax dir] = ~/work/sonoisa-XyJax-xxxxx .

3. Rewrite the source code of the XyJax.
 - Open [XyJax dir]/extensions/TeX/xypic.js.
 - Rewrite the string "[MathJax]/extensions" in the last line to fit your [XyJax loc]. e.g.
   
   >     xypic.js 
   >       before: MathJax.Ajax.loadComplete("[MathJax]/extensions/TeX/xypic.js");
   >       after:  MathJax.Ajax.loadComplete("http://sonoisa.github.io/xyjax_ext/xypic.js");

4. Publish the XyJax to your own server.
 - Publish [XyJax dir]/extensions/TeX/xypic.js to [XyJax loc]/xypic.js. 
 
     e.g. http://sonoisa.github.io/xyjax_ext/xypic.js .

5. Use XyJax on your own site.
 + Like the configuration given below, load MathJax.js and xypic.js within pages on your site.

 >     <script type="text/x-mathjax-config>
 >     MathJax.Hub.Config({
 >       extensions: ["tex2jax.js"],
 >       jax: ["input/TeX","output/HTML-CSS"],
 >       "HTML-CSS": {
 >         styles: {".MathJax_Preview": {visibility: "hidden"}}
 >       },
 >       tex2jax: {inlineMath: [["$","$"],["\\(","\\)"]]},
 >       TeX: {extensions: ["AMSmath.js","AMSsymbols.js","[XyJax loc]/xypic.js"]}
 >       //                                               ^^^^^^^^^^^^^^^^^^^^ rewrite to fit your own server url.
 >     });
 >     </script>
 >     <script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js"></script>
 e.g. (sample: http://sonoisa.github.io/xyjax_ext/sample-xyjax.html )

 >     <script type="text/x-mathjax-config>
 >     MathJax.Hub.Config({
 >       extensions: ["tex2jax.js"],
 >       jax: ["input/TeX","output/HTML-CSS"],
 >       "HTML-CSS": {
 >         styles: {".MathJax_Preview": {visibility: "hidden"}}
 >       },
 >       tex2jax: {inlineMath: [["$","$"],["\\(","\\)"]]},
 >       TeX: {extensions: ["AMSmath.js","AMSsymbols.js","http://sonoisa.github.io/xyjax_ext/xypic.js"]}
 >     });
 >     </script>
 >     <script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js"></script>


### Installation Method 2. Installing XyJax and MathJax on your own server.  

1. Download MathJax source code.
 - Go to the MathJax download site: http://www.mathjax.org/download/
 - Download MathJax source code (ver. 2.3).
 - Extract the MathJax source code to a directory (referred to as [MathJax dir]). e.g. 
 
   >     $ unzip mathjax-MathJax-v2.3-xxxx -d ~/work
   
 In this case, [MaxJax dir] = ~/work/mathjax-MathJax-v2.3-xxxx .
 
2. Download XyJax source code.
 - Go to the XyJax download site (this page).
 - Click the Download Zip button.
 - Extract the downloaded file to a directory (referred to as [XyJax dir]). e.g.

   >     $ unzip  sonoisa-XyJax-xxxxx -d ~/work
   
 In this case, [XyJax dir] = ~/work/sonoisa-XyJax-xxxxx
 
3. Move the XyJax files into the MathJax directory.
 - [XyJax dir]/extensions/TeX/xypic.js &rarr; [MathJax dir]/extensions/TeX/xypic.js
 - [XyJax dir]/test/sample-xyjax.html &rarr; [MathJax dir]/test/sample-xyjax.html
   
   eg.
   >     $ cp ~/work/sonoisa-XyJax-xxxxx/extensions/TeX/xypic.js ~/work/mathjax-MathJax-v2.3-xxxx/extensions/TeX/
   >     $ cp ~/work/sonoisa-XyJax-xxxxx/test/sample-xyjax.html ~/work/mathjax-MathJax-v2.3-xxxx/test/
   
   ![moved files](http://sonoisa.github.com/xyjax/xyjax_images/Moved_XyJax_files2.png)
   
4. Open [MathJax dir]/test/sample-xyjax.html with Firefox/Safari/Chrome.
 + If XyJax works, You can see so-called commutative diagram like this:
 
   ![commutative diagram](http://sonoisa.github.com/xyjax/xyjax_images/CD2.png)

5. Install MathJax on your own server using the source code you created in step 3.
 - Follow the local installation instructions: http://docs.mathjax.org/en/latest/installation.html

6. Use XyJax on your own site.
 + like the configuration of the test/sample-xy.jax, load MathJax.js and xypic.js within pages on your site.

 >     <script type="text/x-mathjax-config>
 >     MathJax.Hub.Config({
 >       extensions: ["tex2jax.js"],
 >       jax: ["input/TeX","output/HTML-CSS"],
 >       "HTML-CSS": {
 >         styles: {".MathJax_Preview": {visibility: "hidden"}}
 >       },
 >       tex2jax: {inlineMath: [["$","$"],["\\(","\\)"]]},
 >       TeX: {extensions: ["xypic.js", "AMSmath.js","AMSsymbols.js"]}
 >       //                  ^^^^^^^^load xypic.js
 >     });
 >     </script>
 >     <script type="text/javascript" src="../MathJax.js"></script>

## Present Limitation

- Supported Browsers:
 - Firefox
 - Safari
 - Chrome
 - Opera
 - Internet Explorer 9 (IE9 Standards Mode only)
- Supported Math Renderer:
 - HTML-CSS
 - SVG (MathJax 2.3 required)
- Currently, XyJax doesn't support MathJax 2.4 or later.

## Current Implementation Status

- See http://sonoisa.github.io/xyjax/xyjax.html#ToDo

## Contact

If you have any questions about XyJax, please let me know.

- e-mail: Isao Sonobe <sonoisa@gmail.com>
