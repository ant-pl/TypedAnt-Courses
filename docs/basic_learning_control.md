## 流程控制

### 条件控制
基本的 `if`、`if else` 和 `else if` 语句在此不再赘述，直接看示例：
```ant
const num = 1u8;
if (num == 1u8) {
    printf("num is 1\n");
}else if (num == 2u8) {
    print("num is 2\n");
}
```

#### 条件控制的更多
`TypedAnt`拒绝太过隐式的控制流, 所以将拒绝`throw`, 错误处理be like:
```ant
if (afunction_may_fail(arg1, arg2).failed) {
    //solve
}
// in the future, `TypedAnt` will add `?*` as option, 
// then u don't have to write code like this
// maybe the code will look like:
/*
if (afunction_may_fail(arg1, arg2)) |err| {
    //solve
}
*/
```

#### 循环
在`TypedAnt`中，循环分为两种，一种是`while`，一种是`for`

#### for
```ant
for(initize; condition; step){
    //...
}
```
like this

#### while
```ant
while(condition){
    //...
}
```

#### continue
`continue`的效果是结束本次循环, 它可能会影响控制流的清晰, 所以建议在循环的开头通过`if`决定是否使用它

#### break
`break`的效果是跳出循环

### defer

`defer`将在当前作用域末尾执行表达式。

如果存在多个 defer，它们将会按照出栈方式执行。

defer 分别可以执行单个语句和一个块，并且如果控制流不经过 defer，则不会执行。

### panic
`panic`是一个标准库函数, 被包含在`err.ta`中。
它会让当前程序异常终止, 并视情况决定是否输出栈追踪, 用法类似`zig`的`unreachable`。

### 跳转
#### 函数调用
like this:
```ant
funcName (arg1, arg2, ...)
```
#### 函数是?
> 一个callable的对象

函数你可以自己定义也可以使用库函数和外部函数

#### 函数如何定义?
```ant
func <func name> ( [func args] ) [ -> <func return value type> ] {
    //func body
}
```

`func`是函数的定义必备的关键字, <func name>是该函数的名称,<br>
[func args]是该函数的参数,<br>
[ -> <func return value type> ]制定了该函数的返回值类型如果不指定则视为无返回值

#### 外部函数是?
> 函数体的实现（定义）位于当前代码的编译单元之外，需通过声明向当前上下文暴露函数接口，使其可被当前代码合法调用的函数。

`TypedAnt`可以这么声明函数:
```ant
extern func <func name> ( [func args] ) [ -> <func return value type> ] ;
```

然后你可以在编译命令中加入`-l...`来把某个`.a`文件链接进来

#### 库函数有哪些?
请查阅库文档

[进入下一篇](./basic_learning_high_level_type.md)
> 下一篇`basic_learning_high_level_type.md`
