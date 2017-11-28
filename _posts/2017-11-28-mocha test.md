---
title: mocha test
---

[阮一峰博客](http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html)

```js
定义 test
const request = require('supertest')
const { createToken } = require('../lib/jwt') //请求 token
const { expect } = require('chai')      
const server = require('../app')   // 这里引用的是 app.listen() 输出的对象
const AV = require('leancloud-storage')
const config = require('../lib/config')

describe('test audioChannel', async() => {
  let api;
  let token;
  beforeEach(async() => {
    api = request(server)
    token = await createToken()
  })
}
```

```js
const Koa = require('koa')
const app = new Koa()
const views = require('koa-views')
const json = require('koa-json')
const onerror = require('koa-onerror')
const bodyparser = require('koa-bodyparser')
const log4js = require('koa-log4')  //koa 日志包
const logger = log4js.getLogger('app')  //这里的 APP 是什么意思

AV.init({
  appId: config.heyzgo.ID,
  appKey: config.heyzgo.Key,
  masterKey: config.heyzgo.MasterKey
});
AV.Cloud.useMasterKey();

.
.
.

let server = app.listen(9999, () => {
  console.log('[demo] request post is starting at port 9999')
})        //这里需要输出 app.listen() 的返回值
          //mocha 需要这引用这个

module.exports = server
```

输出测试结果到网页:
npm install --save-dev mochawesome
mocha testfile.js --reporter mochawesome

-  --growl, -G
打开--growl参数，就会将测试结果在桌面显示。
- --watch，-w
--watch参数用来监视指定的测试脚本。只要测试脚本有变化，就会自动运行Mocha。
- --bail, -b
--bail参数指定只要有一个测试用例没有通过，就停止执行后面的测试用例。这对持续集成很有用。
- --grep, -g
--grep参数用于搜索测试用例的名称（即it块的第一个参数），然后只执行匹配的测试用例。
- --invert, -i
--invert参数表示只运行不符合条件的测试脚本，必须与--grep参数配合使用。

