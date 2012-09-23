# XyJax
 -- Xy-pic extension for MathJax --

----
XyJax is a almost Xy-pic compatible language extension for MathJax.

This extension enable us to draw various graphs and diagrams.

See http://sonoisa.github.com/xyjax/xyjax.html for more details. And origins

- MathJax: http://www.mathjax.org/ (Mother)
- Xy-pic: http://www.tug.org/applications/Xy-pic/ (Father)

But, this software is under development, so this release is alpha-quality (often buggy).


## Installation and Usage

1. Download MathJax source code.
 - Go to the MathJax download site: http://www.mathjax.org/download/
 - Download MathJax source code (ver. >= 2.0).
 - Extract the MathJax source code to a directory (referred to as [MathJax dir]). e.g. 
 
   >     $ unzip mathjax-MathJax-v2.0-xxxx -d ~/work
   
 In this case, [MaxJax dir] = ~/work/mathjax-MathJax-v2.0-xxxx
 
2. Download XyJax source code.
 - Go to the XyJax download site (this page).
 - Click the Downloads button on the upper right side, and click Download zip or tar.gz button.
 - Extract the downloaded file to a directory (referred to as [XyJax dir]). e.g.

   >     $ unzip  sonoisa-XyJax-xxxxx -d ~/work
   
 In this case, [XyJax dir] = ~/work/sonoisa-XyJax-xxxxx
 
3. Move the XyJax files into the MathJax directory.
 - [XyJax dir]/extensions/fp.js &rarr; [MathJax dir]/extensions/fp.js
 - [XyJax dir]/extensions/TeX/xypic.js &rarr; [MathJax dir]/extensions/TeX/xypic.js
 - [XyJax dir]/test/sample-xyjax.html &rarr; [MathJax dir]/test/sample-xyjax.html
   
   eg.
   >     $ cp ~/work/sonoisa-XyJax-xxxxx/extensions/fp.js ~/work/mathjax-MathJax-v2.0-xxxx/extensions/
   >     $ cp ~/work/sonoisa-XyJax-xxxxx/extensions/TeX/xypic.js ~/work/mathjax-MathJax-v2.0-xxxx/extensions/TeX/
   >     $ cp ~/work/sonoisa-XyJax-xxxxx/test/sample-xyjax.html ~/work/mathjax-MathJax-v2.0-xxxx/test/
   
   ![moved files](http://sonoisa.github.com/xyjax/xyjax_images/Moved_XyJax_files.png)
   
4. Open [MathJax dir]/test/sample-xyjax.html with Firefox/Safari/Chrome.
 + If XyJax works, You can see so-called commutative diagram like this:
 
   ![commutative diagram](http://sonoisa.github.com/xyjax/xyjax_images/CD2.png)

5. Install MathJax on your own server using the source code you created in step 3.
 - Follow the local installation instructions: http://www.mathjax.org/docs/2.0/installation.html

6. Use XyJax on your own site.
 + like the configuration of the test/sample-xy.jax, load MathJax.js and fp.js, xypic.js within pages on your site.

 >     <script type="text/x-mathjax-config>
 >     MathJax.Hub.Config({
 >       extensions: ["tex2jax.js","fp.js"],
 >       //                         ^^^^^load fp.js
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

- Supported Browsers: Firefox, Safari, Chrome, Opera, Internet Explorer 9 (IE9 Standards Mode only)
- Supported Math Renderer: HTML-CSS

## Current Implementation Status

- See http://sonoisa.github.com/xyjax/xyjax.html#ToDo

## Contact

If you have any questions about XyJax, please let me know.

- e-mail: Isao Sonobe <sonoisa@gmail.com>
