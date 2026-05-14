## 高级类型

### 指针
> 作为一门语言，TypedAnt支持指针

指针是内存地址。通过指针，我们可以间接访问和操作其指向的内存区域。

取地址：通过`&`符号来获取变量的内存地址。  
(**`还没写`**)

解引用：通过`*`符号来解引用。

指针的加减：可以直接与整数类型相加减  
这本身其实是一个语法糖，例:
```ant
extern "C" func malloc(size: usize) -> *u8;

const ptr = malloc(4usize); //*i32类型
ptr + 1usize; // 实际编译为 ptr + (sizeof i32) * 1
```

### 字符串

大家都知道字符串是 "Hello, world!" 这种格式。我们经常需要在源代码中定义字符串，例如某些提示信息。  
通常，这种直接嵌入源代码的字符串被称为硬编码字符串 (又称**字符串字面量**)。  
字符串字面量在编译器中会被编译到可执行文件的 **.rodata** 段 (**只读段**)  

> [!NOTE]
> 你不能修改一个**字符串字面量**

##### 字符串定义

在`TypedAnt`中，字符串字面量是一个指向以`0`结尾的`u8`数组的指针。因此，对其解引用则会得到数组的第一个元素。

### 结构体

结构体是一种高级数据结构，用于将多个相关数据组织成一个单一的实体。

#### 基本语法

以下是一个简短的示例：

```ant
struct Vec<T> {
    item: *T,
    len: usize
    // ...
}
```

> [!NOTE]
> 注意: 使用逗号分隔字段

#### 初始化

```ant
let o = new Vec {
    item = malloc(4) as *i32
    len = 1
};
```
一看便知

#### 默认值
```ant
struct Circle {
    radios: u8 = 0,
    exist: bool
}
```
结构体允许为字段设置默认值，只需在定义结构体时声明即可

#### 空结构体
```ant
struct Gunmu {}
// a empty struct
```

[进入下一篇](./basic_learning_control.md)
> 下一篇`basic_learning_control.md`
