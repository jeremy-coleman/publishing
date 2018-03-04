publishing
notes

npm login --scope=@coglite
jeremy-at-coglite
(password)
coglite@outlook.com (or official) idk

then..

npm publish --access public
(i think public flag is only required for first pkg)  


```javascript
const argv = require('yargs').argv
const shelljs = require('shelljs')
const {promisify} = require('util')
const fs = require('fs')


const {package, onlyPublish} = argv

process.nextTick(async () => {

  if (!!package) {
    shelljs.cd(`packages/${package}`)
    if (onlyPublish) return shelljs.exec(`npm publish --access=public`)
    shelljs.exec(`rm -f *.js`)
    shelljs.exec(`babel src -d .`)
    shelljs.exec(`npm publish --access=public`)
    shelljs.exec(`rm -f *.js`)
  }
})
```
