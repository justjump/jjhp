---
title: PHP基本操作归纳总结
date: 2016-06-11 13:47:03
categories: 经验
tags:
---
### 创建数组
[参考W3教程](http://www.w3school.com.cn/php/php_arrays.asp)
#### 重点
1. 定义:`$cars=array("Volvo","BMW","SAAB");`
2. 数组长度:```<?php
$cars=array("Volvo","BMW","SAAB");
echo count($cars);
?>```
3. 遍历数组```
<?php
$cars=array("Volvo","BMW","SAAB");
$arrlength=count($cars);

for($x=0;$x<$arrlength;$x++) {
  echo $cars[$x];
  echo "<br>";
}
?>
```