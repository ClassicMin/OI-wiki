**联合体**（union）是特殊的类类型，它在一个时刻只能保有其一个非静态数据成员。

联合体在 2023 年正式被加入 NOI 大纲入门级中。

## 定义联合体

联合体声明的类说明符与类或 [结构体](./struct.md) 的声明相似：

```cpp
union MyUnion {
  int x;
  long long y;
} x;
```

联合体的定义与结构体类似。按照上述定义，`MyUnion` 同样可以当作一种自定义类型使用。名称 `MyUnion` 可以省略。

## 联合体的初始化

实例:
```cpp
union MyUnion {
  int x;
  long long y;
};
MyUnion u={.y=17};
```

## 访问/修改成员元素

与结构体类似，同样可以使用 `变量名.成员名` 进行访问。

联合体所占用的内存空间大小 **不小于** 其最大的成员的大小，所有成员 **共用内存空间与地址**。当一个成员被赋值，由于内存共享，该联合体中的其他成员都会被覆盖。即同一时刻联合体中只能保存一个成员的值。

联合体的更多用法可以参见 [cppreference：联合体声明](https://zh.cppreference.com/w/cpp/language/union)。

例题 [1041 - CSP 2023 入门级第一轮 第三题](https://ti.luogu.com.cn/problemset/1041)。
