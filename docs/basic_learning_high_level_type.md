## 高级类型

### Vec

> Vec 提供了一种对一组同类型（布尔、整型、浮点、指针）值进行操作的方法。

Vec 类型通过库函数`vec_init`创建。

---

#### 基本使用

```ant
use stl; // use 没写, 请直接替换为stl.ta的内容

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

#### True 基本使用
其实, 上面的`基本使用`基本没用, u may have to read [STL-Vec文档](./Vec.md)

### 指针
> 作为一门语言，TypedAnt支持指针

指针是内存地址。通过指针，我们可以间接访问和操作其指向的内存区域。

取地址：通过`&`符号来获取变量的内存地址。  
(**`我还没写`**)

解引用：通过`*`符号来解引用。

指针的加减：可以直接与整数类型相加减  
这本身其实是一个语法糖，例:
```ant
extern "C" func malloc(size: usize) -> *u8;

const ptr = malloc(4usize); //*i32类型
ptr + 1usize; // 等价于 ptr + (sizeof i32) * 1
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
let o= new Vec {
    item = malloc(4) as *i32
    len = 1
};
//note: 标准库中Vec的init和insert等设计申请内存的函数均有问题, 马上改
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
好吧, boku暂时不知道这有什么用, 因为boku拒绝任何throw, 同时map还没写...

[进入下一篇](./control.md)
> 下一篇`control.md`
