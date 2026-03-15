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
`panic`是一个标准库函数, 被包含在`exception.ta`或`error.ta`中(未定)。
它会让当前程序异常终止, 并视情况决定是否输出栈追踪, 用法类似`zig`的`unreachable`。

[进入下一篇](./basic_learning_high_level_type.md)
> 下一篇`basic_learning_high_level_type.md`
