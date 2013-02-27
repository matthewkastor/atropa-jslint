# atropa-jslint

A node module wrapper for jslint.

All this does is export the jslint function, and allow you to update the jslint version easily, it's simple.

## General use
See `lib/jslint.js` for full documentation on jslint.

```
var os = require('os');
var fs = require('fs');
var jslint = require('atropa-jslint');
var result = jslint.JSLINT(fs.readFileSync('somefile.js'));
if(result) {
    console.log('no errors found!');
} else {
    jslint.JSLINT.errors.forEach(function (error) {
        console.error(
            '* Error:' + os.EOL +
            '    Reason: ' + error.reason + os.EOL +
            '    Evidence: ' + error.evidence + os.EOL +
            '    Line: ' + error.line + os.EOL +
            '    Char: ' + error.character + os.EOL + os.EOL
        );
    });
}
```


## Update to the JsLint version.

```
var jslint = require('atropa-jslint');
jslint.update();
```


## Rollback to the previous JsLint version.

```
var jslint = require('atropa-jslint');
jslint.rollbackUpdate();
```