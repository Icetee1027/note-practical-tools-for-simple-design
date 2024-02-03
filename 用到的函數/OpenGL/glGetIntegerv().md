
----
 `glGetIntegerv` 函数属于 [[OpenGL]]（OpenGL ES 1.0 及以上版本），用于获取指定参数的整型值。

**函数原型：**
```cpp
void glGetIntegerv(GLenum pname, GLint *params);
```

**参数：**
- `pname`：要查询的参数名称，可以是 [[OpenGL]] 的常量之一，如 `GL_MAX_TEXTURE_SIZE`。
- `params`：存储获取到的整型值的数组的指针。

**返回值：**
- 无。

**说明：**
`glGetIntegerv` 函数用于获取指定参数的整型值，并将其存储在 `params` 所指向的数组中。参数 `pname` 指定了要查询的参数名称，而 `params` 参数是一个指向整型数组的指针，用于存储获取到的值。根据查询的参数不同，`params` 数组可能包含一个或多个整型值。

**示例用法：**
```cpp
GLint maxTextureSize;
glGetIntegerv(GL_MAX_TEXTURE_SIZE, &maxTextureSize);
std::cout << "Max texture size: " << maxTextureSize << std::endl;
```

**注意事项：**
- 在调用 `glGetIntegerv` 函数之前，应先了解要查询的参数的含义和取值范围，以确保正确获取所需的信息。
- 传递给 `params` 参数的数组应具有足够的大小，以存储要获取的整型值。