#1  
https://github.com/convoyinc/deep-update  
react-addons-update, except that it will fill in object paths that are missing.  
 ```javascript
const value = {a: {b: {c: {d: 1234}}}};
// Behold, no error thrown!
const newValue = deepUpdate(value, ['a', 'b', 'c', 'd'], {$set: 2345});
```
