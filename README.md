﻿# QuickScore.js

把 [QuickScore](https://github.com/fwextensions/quick-score) 整体打包到一个文件

## 用法

```js
<script src="quicksore.js"></script>
  <script>
    var qs = new QuickScore(["poerlang" , "客服CRM", "cr_GitHub_m","crm客服", "hello_m_r"]);
    var results = qs.search("crm");
    console.log(results);
  </script>
```

output:


```js
[{
	"item": "crm客服",
	"score": 0.96,
	"matches": [
		[0, 3]
	],
	"_": "crm客服"
}, {
	"item": "客服CRM",
	"score": 0.9399999999999998,
	"matches": [
		[2, 5]
	],
	"_": "客服crm"
}, {
	"item": "cr_GitHub_m",
	"score": 0.827272727272727,
	"matches": [
		[0, 2],
		[10, 11]
	],
	"_": "cr_github_m"
}]
```

## 更新数组,重新搜索的方法

```js
qs.setItems(['abc', 'add']);
results = qs.search("a");
console.log(results)
```

## 根据某些自定义字段来搜索

```js
var lists = [
        {name:'crm',objref:1,title:'a crm client'},
        {name:'good',objref:1,title:'things'}
    ]
var qs = new QuickScore(lists,['name','title']);
var results = qs.search("cr");
console.log(results);
```
