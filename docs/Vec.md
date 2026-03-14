## STL文档

### Vec

> Vec 提供了一种对一组同类型（布尔、整型、浮点、指针）值进行操作的方法。

Vec 类型通过库函数`vec_init`创建。

---

#### Vec本体

```ant
struct Vec<T> {
    ptr: *T,
    size: usize
}
```
**!!!注意!!!**
> **无论如何**, 你不能使用`.`来访问Vec的**任何**成员!<br>
你需要使用vec_*一系列函数

#### Functions about Vec

##### vec_init
原型:
```ant
func vec_init<T>(size_: usize) -> Vec<T>
```

描述:
> 创建一个`Vec`, 长度为`size_`

##### vec_free
原型:
```ant
func vec_free<T>(v: Vec<T>)
```

描述:
> 释放一个`Vec`

##### vec_get
原型:
```ant
func vec_get<T>(v: Vec<T>, p: u8)-> T
```

描述:
> 获得位于一个`Vec`中的第`p`个元素(索引从0开始)的值

##### vec_post
原型:
```ant
func vec_post<T>(v: Vec<T>, p: u8, nv: T)
```

描述:
> 设置位于一个`Vec`中的第`p`个元素(索引从0开始)的值为`nv`

##### vec_ref
原型:
```ant
func vec_ref<T>(v: Vec<T>, p: u8) -> *T
```

描述:
> 获得一个指向位于一个`Vec`中的第`p`个元素(索引从0开始)的指针

##### vec_size
原型:
```ant
func vec_size<T>(v: Vec<T>) -> usize
```

描述:
> 获得一个`Vec`中的长度

##### vec_erase
原型:
```ant
func vec_erase<T>(v: Vec<T>, p:u8) -> Vec<T>
```

描述:
> 删去一个`Vec`中的第`p`个元素(索引从0开始)

##### vec_insert
原型:
```ant
func vec_insert<T>(v: Vec<T>, p: u8, nv: T) -> Vec<T>
```

描述:
> 将`nv`插入一个`Vec`中的第`p`个元素(索引从0开始)的位置

##### vec_find
原型:
```ant
func vec_find<T> (v: Vec<T>, content: T) -> *T
```

描述:
> 获得一个指向第一个一个`Vec`中的值等于`content`的元素(索引从0开始)的指针

> 剩下的明天boku再写...

[返回引用处-高级类型](./basic_learning_high_level_type.md)
