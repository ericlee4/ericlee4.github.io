# svg redirect
~![square](https://ericlee4.github.io/square.svg)~

Messing around with trying to bypass CSP and find XSS vulnerabilities. I'm
embedding an HTML page within an SVG and using the meta refresh element to
redirect to another domain. You can link images to other websites but this
redirects from github's githubusercontent domain to another domain which is
slightly misleading.

```
<svg xmlns="http://www.w3.org/2000/svg">
   <foreignObject style="width: 100%; height: 100%">
   <html xmlns="http://www.w3.org/1999/xhtml">
      <head>
         <meta http-equiv="refresh" content="0; url=https://ericlee.dev" />
      </head>
      <body>
         <div style="width: 500px; height: 500px; color: white; background: gray;display: flex;justify-content: center;align-items: center;">
Click on this SVG
         </div>
      </body>
   </html>
   </foreignObject>
</svg>
```
