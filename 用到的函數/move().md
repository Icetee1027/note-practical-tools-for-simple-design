
----
`std::move` 是一个 C++11 引入的函数，用于将对象转移（move）为右值引用，通常用于实现移动语义，提高程序的性能。

**函数原型：**
```cpp
template< class T >
constexpr std::remove_reference_t<T>&& move( T&& t ) noexcept;
```

**参数：**
- `t`：要被转移的对象。

**返回值：**
- 返回一个右值引用，指向参数 `t` 的内容。

**说明：**
- `std::move` 不会实际移动对象的内容，它只是将对象转换为右值引用，告诉编译器可以使用移动语义。
- 移动语义是一种优化手段，通常用于在不需要保留原始对象内容的情况下，将其内容转移到另一个对象中，以提高性能和效率。
- 移动语义通常与移动构造函数和移动赋值运算符一起使用，这些特殊的成员函数允许对象的内容被移动到另一个对象中，而不是复制。

**示例用法：**
```cpp
#include <iostream>
#include <utility>

class MyObject {
public:
    MyObject() {}
    MyObject(const MyObject&) {
        std::cout << "Copy constructor\n";
    }
    MyObject(MyObject&&) noexcept {
        std::cout << "Move constructor\n";
    }
};

int main() {
    MyObject obj1;
    MyObject obj2 = std::move(obj1); // 使用移动语义将 obj1 转移到 obj2 中

    return 0;
}
```

**注意事项：**
- 使用 `std::move` 后，原始对象的状态变为未指定，不应再使用该对象。
- 移动语义通常用于容器类中的元素移动、智能指针的转移等场景，以提高性能和效率。
- 在不需要保留原始对象内容的情况下，应该优先考虑使用移动语义而不是复制。