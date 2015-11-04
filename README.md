# lei-proto
简单的Buffer编码/解析模块

## 安装

```bash
$ npm install lei-proto
```


## 使用

```javascript
var parseProto = require('lei-proto');

var p = parseProto([
  ['a', 'uint', 1],
  ['b', 'int', 1],
  ['c', 'float'],
  ['d', 'double'],
  ['e', 'string', 1],
  ['f', 'buffer', 1]
]);

var b = p.encode(1, 2, 3.3, 4.4, 'a', new Buffer('b'));
var c = p.decode(b);
console.log(b, c);
```

规则：`['名称', '数据类型', 长度, '字节顺序BE/LE']`

具体使用方法参考单元测试


## The MIT License

```
The MIT License (MIT)

Copyright (c) 2015 Zongmin Lei <leizongmin@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
