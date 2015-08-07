# jscs-exlude-files-bug [![Build Status](https://travis-ci.org/iamstarkov/jscs-exlude-files-bug.svg?branch=master)](https://travis-ci.org/iamstarkov/jscs-exlude-files-bug)

```
git clone git@github.com:iamstarkov/jscs-exlude-files-bug.git
cd jscs-exlude-files-bug
npm install
npm run jscs
```


## jscs tries to validate excluded files
```
➜  jscs-exlude-files-bug git:(master) ✗ cat .jscsrc
{
  "plugins": ["jscs-config-nordnet"],
  "preset": "nordnet",
  "excludeFiles": [
    "app/templates/_index.test.js"
  ]
}
➜  jscs-exlude-files-bug git:(master) ✗ npm run jscs
> jscs-exlude-files-bug@1.0.0 jscs /Users/vlasta/projects/jscs-exlude-files-bug
> jscs app

parseError: undefined at app/templates/_index.test.js :
     1 |import sinon from 'sinon';
     2 |import { expect } from 'chai';
     3 |import <%= camelModuleName %> from './../src/index';
---------------^
     4 |
     5 |describe('<%= camelModuleName %>', () => {


1 code style error found.
```
