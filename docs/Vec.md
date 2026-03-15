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

---

#### Functions about Vec

##### vec_init
原型:
```ant
func vec_init<T>(size_: usize) -> Vec<T>
```
描述:
> 创建一个`Vec`, 容量和长度均为`size_`

##### vec_free
原型:
```ant
func vec_free<T>(v: Vec<T>)
```
描述:
> 释放`Vec`占用的所有内存

##### vec_inita
原型:
```ant
func vec_inita<T>(size_: usize, first: T) -> Vec<T>
```
描述:
> 创建一个`Vec`并插入初始元素`first`

##### vec_get
原型:
```ant
func vec_get<T>(v: Vec<T>, p: usize) -> T
```
描述:
> 获得`Vec`中第`p`个元素的值(索引从0开始)

##### vec_post
原型:
```ant
func vec_post<T>(v: Vec<T>, p: usize, nv: T)
```
描述:
> 设置`Vec`中第`p`个元素的值为`nv`(索引从0开始)

##### vec_ref
原型:
```ant
func vec_ref<T>(v: Vec<T>, p: usize) -> *T
```
描述:
> 获取指向`Vec`第`p`个元素的指针(索引从0开始)

##### vec_size
原型:
```ant
func vec_size<T>(v: Vec<T>) -> usize
```
描述:
> 获取`Vec`的当前有效长度

##### vec_empty
原型:
```ant
func vec_empty<T>(v: Vec<T>) -> bool
```
描述:
> 判断`Vec`是否为空，空返回true，非空返回false

##### vec_begin
原型:
```ant
func vec_begin<T>(v: Vec<T>) -> *T
```
描述:
> 获取`Vec`首元素的指针

##### vec_end
原型:
```ant
func vec_end<T>(v: Vec<T>) -> *T
```
描述:
> 获取`Vec`末尾元素的下一个指针

##### vec_erase
原型:
```ant
func vec_erase<T>(v: Vec<T>, p: usize)
```
描述:
> 删除`Vec`中第`p`个元素，长度减1(索引从0开始)

##### vec_insert
原型:
```ant
func vec_insert<T>(v: Vec<T>, p: usize, nv: T)
```
描述:
> 在`Vec`第`p`个位置插入元素`nv`，长度加1(索引从0开始)

##### vec_push
原型:
```ant
func vec_push<T>(v: Vec<T>, nv: T)
```
描述:
> 在`Vec`末尾追加元素`nv`

##### vec_pop
原型:
```ant
func vec_pop<T>(v: Vec<T>)
```
描述:
> 删除`Vec`末尾的元素，长度减1

##### vec_find
原型:
```ant
func vec_find<T> (v: Vec<T>, content: T) -> *T
```
描述:
> 查找第一个值等于`content`的元素，返回其指针；未找到返回末尾指针

##### vec_swap
原型:
```ant
func vec_swap<T>(v: Vec<T>, i: usize, j: usize)
```
描述:
> 交换`Vec`中第`i`和第`j`个元素的值

##### vec_resize
原型:
```ant
func vec_resize<T>(v: Vec<T>, new_cap: usize)
```
描述:
> 修改`Vec`容量；容量小于长度时截断数据并修改长度

##### vec_data
原型:
```ant
func vec_data<T>(v: Vec<T>) -> *T
```
描述:
> 获取`Vec`数据存储区的原始指针

##### vec_build
原型:
```ant
func vec_build<T>(raw: *T, len: usize) -> Vec<T>
```
描述:
> 从原始指针深拷贝数据，创建新的`Vec`

##### vec_copy
原型:
```ant
func vec_copy<T>(ov: Vec<T>) -> Vec<T>
```
描述:
> 深拷贝一个已有的`Vec`，返回新副本

[返回引用处-高级类型](./basic_learning_high_level_type.md)