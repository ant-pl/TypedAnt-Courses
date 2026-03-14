## 变量

在`TypedAnt`中，我们使用`let`关键字来声明变量，  
其格式为`let variable_name: Type = initial_value;`。以下是一个示例：

```ant
func foo() {
    //声明变量 variable 类型为u16, 并指定值为 666
    let variable: u16 = 0u16;
    variable = 666u16;
}
```

### 标识符命名
在`TypedAnt`中，标识符必须以字母或下划线开头，
后跟任意字母、数字或下划线，并且不得与关键字重叠。

### 常量
`TypedAnt`使用 const 关键字来声明常量。常量一旦声明并赋值后，其值便不可更改，只能在初次声明时进行赋值。

> [!NOTE]
注意: 常量的命名规范为 **`大写下划线`**

```ant
extern "C" func printf(s: str, ...) -> i32;

const CONSTANT: u16 = 666u16;

func foo() {
    printf("常量 CONSTANT 是%d\n", CONSTANT);
}
```

[进入下一篇](https://github.com/langhat/TypedAnt-Courses/blob/main/docs/basic_learning_type.md)
> 下一篇`basic_learning_type.md`
