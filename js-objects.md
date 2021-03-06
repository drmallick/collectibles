
In JavaScript, null is an object. There's another value for things that don't exist, undefined. The DOM returns null for almost all cases where it fails to find some structure in the document, but in JavaScript itself undefined is the value used.

Second, no, there is not a direct equivalent. If you really want to check for null, do:

if (null == yourvar) // With casting
if (null === yourvar) // Without casting
If you want to check if a variable exists

if (typeof yourvar != 'undefined') // Any scope
if (window['varname'] != void 0) // Old browsers
If you know the variable exists, but don't know if there's any value stored in it:

if (undefined != yourvar)
if (void 0 != yourvar) // For older browsers
If you want to know if a member exists independent of whether it has been assigned a value or not:

if ('membername' in object) // With inheritance
if (object.hasOwnProperty('membername')) // Without inheritance
If you want to to know whether a variable autocasts to true:

if(variablename)
Don't do this, because there is no constant named undefined. It will work, but only so long as someone doesn't create a variable named undefined:

if (window['varname'] != undefined)
I probably forgot some method as well...

Source: http://stackoverflow.com/questions/858181/how-to-check-a-not-defined-variable-in-javascript
