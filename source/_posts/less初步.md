---
title: less初步
date: 2017-11-14 8:00:00
tags:
---
# less初步

## 注释

注释分为两种：

- /* 我是注释 */
- // 我是注释

区别在于，第一种编译后会保留，而第二种不会保留。

<!--more-->

## 变量

变量定义：  `@key:value; `

LESS 中的变量为完全的 ‘常量’ ，所以只能定义一次。

## 混合

- 基本用法

```less
variable{
  property: value;
}
selector{
  variable;
  others:...;
}
```

- 带参数

```less
variable(@key){
  property: some other @key;
}
selector{
  variable(value);
}
```

- 带默认值

```less
variable(@key:default){
  property: some other @key;
}
selector{
  variable();
  // or
  // variable(value)
}
```

## 匹配模式

```less
variable(condition1){
  property:...;
}
variable(condition2){
  property:...;
}
variable(@_){	// 通用
  commonProperty:...;
}

selector{
  variable(condition1);
}
```

## 运算

```less
@variable:value;
variable{
  property: value + @variable;	//如果value为10px，@variable为10，也可以进行运算
}
```

## 嵌套

```less
parentSelector{
  property:value;
  
  childSelector{
    property:value;
    
    // &表示上一层选择器，如下面所示，表示的是childSelector:hover
    &:hover{
      //...
    }
  }
}
```

## arguments

``@arguments``包含了所有传递进来的参数

```less
variable(@key1:default, @key2:default){
  property: @arguments;
}
```

## 避免编译

用``~'...'``包裹不需要编译的内容。

## !important

在分号前增加``!important``即可为语句增加``!important``。

----

这些是less的常用功能，除此之外，还有导引、Color函数、Math函数、命名空间、作用域、Importing、字符串插值、JavaScript表达式等，将在下一篇进行说明。
