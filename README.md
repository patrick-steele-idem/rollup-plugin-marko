markoify
========

This Browserify transform results in any referenced Marko templates to automatically be compiled and bundled up so that the templates can be rendered in the browser.

# Installation

```bash
npm install markoify --save
```

# Usage:

```bash
browserify -t markoify main.js > browser.js
```

# Example

__my-project/template.marko:__

```html
Hello ${data.name}!
```

__my-project/main.js:__

```javascript
var template = require('marko').load(require.resolve('./template.marko'));
template.render({
        name: 'World'
    },
    function(err, output) {
        console.log('Output: ', output)
    });
```

```bash
browserify -t markoify main.js > browser.js
```

Page HTML:

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Marko+Browserify Test</title>
    </head>
    <body>
        <script src="browser.js"></script>
    </body>
</html>
```

Browser output:

```
Output: Hello World!
```

# Further Reading

* [Marko](https://github.com/raptorjs/marko)
* [RaptorJS Optimizer](https://github.com/raptorjs/optimizer) (alternative to Browserify)

# Discuss

Please post questions or comments on the [RaptorJS Google Groups Discussion Forum](http://groups.google.com/group/raptorjs).

# Contributors

* [Patrick Steele-Idem](https://github.com/patrick-steele-idem) (Twitter: [@psteeleidem](http://twitter.com/psteeleidem))

# Contribute

Pull Requests welcome. Please submit Github issues for any feature enhancements, bugs or documentation problems.

# License

Apache License v2.0
