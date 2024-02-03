
----
### 函数介绍

**所属及用途：** `glUniformBlockBinding` 函数属于 OpenGL（OpenGL 3.1 及以上版本），用于将指定的统一块绑定到指定的统一缓冲绑定点。

**函数原型：**
```cpp
void glUniformBlockBinding(GLuint program, GLuint uniformBlockIndex, GLuint uniformBlockBinding);
```

**参数：**
- `program`：指定程序对象的名称，即包含要绑定的统一块的着色器程序对象。
- `uniformBlockIndex`：指定要绑定的统一块的索引，即通过 `glGetUniformBlockIndex` 获取到的统一块索引。
- `uniformBlockBinding`：指定要绑定的统一缓冲绑定点，即用于在着色器中访问该统一块数据的绑定点。

**说明：**
`glUniformBlockBinding` 函数用于将指定的统一块绑定到指定的统一缓冲绑定点。统一缓冲绑定点是用于在 OpenGL 程序中指定统一缓冲对象的绑定点，使得该统一缓冲对象中的数据可以在着色器程序中进行访问。

**示例用法：**
```cpp
GLuint program = // 着色器程序对象的名称
GLuint uniformBlockIndex = // 统一块索引
GLuint uniformBlockBinding = 0; // 统一缓冲绑定点
glUniformBlockBinding(program, uniformBlockIndex, uniformBlockBinding);
```

**注意事项：**
- 在调用 `glUniformBlockBinding` 函数之前，需要确保指定的着色器程序对象已经成功链接。
- 统一缓冲绑定点是一个整数值，用于指定在着色器程序中访问该统一块数据的绑定点。需要保证该绑定点的值在有效范围内。
- 一旦统一块绑定到统一缓冲绑定点后，该统一缓冲对象将会被绑定到指定的绑定点上，使得着色器程序可以访问该统一缓冲对象中的数据。