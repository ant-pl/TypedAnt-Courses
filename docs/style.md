## `TypedAnt`代码风格

### 1. 缩进
- 统一使用 **Tab** 缩进
- 结构体、函数、if、while、for 内部必须缩进一层

### 2. 大括号 `{ }`
- 统一跟在语句同一行末尾

```ant
func func_name<T>() {
}

if a {
}
```

### 3. 命名
- 结构体：TitleCase
- 函数：snake_case, 只给内部使用，不暴露给用户的函数请使用`_`开头
- 变量：snake_case
- 常量: 这是复杂的问题, 见下文
- 循环变量等不重要的可用 `i`、`j`等令人不适的名字(Although 不推荐)

### 4. 空格
- 运算符两边留空格：`a + b`、`i = i + 1`
- `sizeof T`、`as` 转换两边留空格
- 参数之间逗号后留空格
- 指针紧贴类型：`*T`、`*u8`，不写 `* T`

### 5. 语句格式
- if / while / for 括号内不留多余空格
- 多行语句必须用大括号
- 单表达式返回可以不写 `return`，分支返回必须写 `return`

### 6. 结构体
- 每个字段独占一行
- 冒号紧贴字段名
- 只给内部使用，不暴露给用户的底层结构体应使用`_`开头
- TiTleCase

### 7. 函数
- 泛型`<T>`紧跟函数名
- 参数列表整齐，类型写清楚
- 函数之间空一行分割
- 功能单一，不要太长太乱

### 8. 常量
如果你是
- Java
- C#
- Python
- JavaScript / TypeScript
- PHP
- Ruby
- Rust
- Swift
- Kotlin
- Objective-C
用户:
UPPER_SNAKE_CASE

如果你是
- Lua
- Julia
- Perl
- C
- Cpp
- Zig
用户:
snake_case

如果都有涉猎:
如果是作为一个暴露到外界的常量, UPPER_SNAKE_CASE
否则, snake_case

### 9. 使用禁忌
- 不写完全看不懂的极简简写
