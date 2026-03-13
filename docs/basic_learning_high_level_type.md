## 高级类型
### 数组

数组是日常编程中使用相当频繁的数据类型之一，在`TypedAnt`中，数组的内存分配方式与`C`类似：在内存中连续分配固定数量的相同类型的元素。

因此，数组具有以下三个特性：

- 长度固定
- 元素必须有相同的类型
- 依次线性排列

---

#### 创建数组

在`TypedAnt`中，你可以使用以下方式来声明并定义一个数组：
```
// aaaaaaa!
// LKBaka没说, boku不知道
```

以上代码展示了如何定义一个字面量数组。其中，你可以明确指定数组的大小，也可以使用 _ 让`TypedAnt`自动推断数组的长度。

数组元素是连续存放的，因此我们可以通过下标来访问数组元素。下标索引从 0 开始。

---

### 向量

> 向量（Vector）提供了一种对一组同类型（布尔、整型、浮点、指针）值进行并行操作的方法，它会尽可能利用 SIMD（单指令多数据）指令集（但boku没有这么做）。

向量类型通过库函数`vec_init`创建。

---

#### 基本使用

```ant
import stl;//暂不支持import, 请直接替换为stl.ta的内容

func main() -> i32 {
    const v = vec_init<u8>(5);
    vec_post(v,0,'h');
    vec_post(v,1,'e');
    vec_post(v,2,'l');
    vec_post(v,3,'l');
    vec_post(v,4,'o');
    vec_insert(v,5,0);
    vec_free(v);
}
```

> 提示
将可以使用`vec_2arr`将向量转换为数组(请等待boku写和LKBaka审pr...)。

### 指针
> 作为一门语言，TypedAnt支持指针

指针是内存地址。通过指针，我们可以间接访问和操作其指向的内存区域。

取地址：通过`&`符号来获取变量的内存地址。

解应用：通过`*`符号来解应用。

指针的加减：可以直接与int相加减<br>
这本身其实是一个语法糖，for example:
```ant
let a = 0u32;
const ptr = &a;//*u32类型
ptr+2;//等价于ptr(是u64)+2*4; (boku假设你使用x64架构设备)
```

### 字符串

> 在深入探讨字符串之前，我们首先明确一个基本概念：计算机中的所有数据都以二进制形式存储。
大家都知道字符串是“Hello, world!”这种格式。我们经常需要在源代码中定义字符串，例如某些提示信息。通常，这种直接嵌入源代码的字符串被称为硬编码字符串。
那么，这些字符串被放在哪里呢？
由于字符串通常是只读的（运行时生成的字符串是另一种情况），它们被存储在二进制程序的只读数据段中。对于相同的字符串字面量，编译器通常只会保留一个副本，这被称为 字符串驻留（String interning）。
MIT License
Copyright (c) 2023 zig-course
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

---

上面的内容是boku摘录的，摘自zig圣经

##### 字符串定义

在`TypedAnt`中，字符串字面量是一个指向以`0`结尾的`u8`数组的指针。因此，对其解引用则会得到数组的第一个元素。

### 结构体

结构体是一种高级数据结构，用于将多个相关数据组织成一个单一的实体。

#### 基本语法

结构体的组成：

> 首部关键字 struct,
多个成员
[模板]

以下是一个简短(?)的结构体模板声明：

```ant
struct Circle<T> {
    radius: T
}
```

上面的代码展示了以下内容：
> 定义了一个结构体模板`Circle`，用于表示一个圆<br>
包含`radius`

[进入下一篇](https://github.com/langhat/TypedAnt-Courses/blob/main/docs/basic_learning_high_level_type.md)
> 下一篇`basic_learning_high_level_type.md`