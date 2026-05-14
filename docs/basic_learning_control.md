## 流程控制

### 条件控制
基本的 `if`、`if else` 和 `else if` 语句在此不再赘述，直接看示例：
```ant
let num = 1u8;
if num == 1 {
    printf("num is 1\n");
} else if num == 2 {
    print("num is 2\n");
}
```

#### Try-Catch-Throw
别想了根本没有, 等写完 enum 老老实实写 Result

#### 循环
在`TypedAnt`中，循环分为两种，一种是`while`，一种是`for`

#### for
```ant
for i in 0..10 {
    // ...
}
```
like this

#### while
```ant
while condition {
    // ...
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

#### extern
> 函数体的实现（定义）位于当前代码的编译单元之外，需通过声明向当前上下文暴露函数接口，使其可被当前代码合法调用的函数。(TypedAnt 原生库不需要)

`TypedAnt` 可以这么声明函数:
```ant
extern "C" func <func name> ( [func args] ) [ -> <func return value type> ] ;
```

然后你可以在编译命令中加入`-l...`来把某个`.a`文件链接进来

[进入下一篇](./basic_learning_high_level_type.md)
> 下一篇`basic_learning_high_level_type.md`
