# XyJax built for the MathJax third party repository
 -- Xy-pic extension for MathJax --


A single-file built of XyJax for the [MathJax third party extension repository](https://github.com/mathjax/MathJax-third-party-extensions), including a compressed version using the [MathJax-dev tools](https://github.com/mathjax/mathjax-dev).

Note that this file combines the original `xypic.js` and `fp.js` and modifies the `MathJax.loadComplete` call to `MathJax.Ajax.loadComplete("[contrib]/xyjax/xypic.js");`.

Note that this URL structure requires MathJax v2.4 and a configured third party path variable, e.g.

        <script type="text/x-mathjax-config">
        MathJax.Ajax.config.path["Extra"] = "http://my.extensions.com/mathjax/contrib";
        </script>
