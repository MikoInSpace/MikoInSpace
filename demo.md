This is the demo page!

The link below and the markdown footer was generated with this NodeJS script:

```js
let GitHubCopy = require("./generator.js"); // Import the generator script
let thisCodeBlock = String(require('fs').readFileSync("./demo.md")).match(new RegExp("\u0060\u0060\u0060js[^\u0060]+\u0060\u0060\u0060"))[0].substr(5,String(require('fs').readFileSync("./demo.md")).match(new RegExp("\u0060\u0060\u0060js[^\u0060]+\u0060\u0060\u0060"))[0].length-8); // horrific regular expressions, just ignore this
let result = GitHubCopy.generate([thisCodeBlock], "https://lxhom.github.io/GitHubCopy/demo", false, true, "JS Footer"); // Call the generate function (see JSDoc in generator.ts for more)
console.log("Copy Link:", result.urls[0].url); // Show the link in the console
console.log("Footer Markdown:", result.markdown); // Show the markdown in the console
```