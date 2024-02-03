
---
### 函数介绍

**所属及用途：** `glGetUniformBlockIndex` 函数属于 OpenGL（OpenGL 3.1 及以上版本），用于获取指定程序对象中的统一块索引。

**函数原型：**
```cpp
GLuint glGetUniformBlockIndex(GLuint program, const GLchar *uniformBlockName);
```

**参数：**
- `program`：指定程序对象的名称，即要查询的着色器程序对象。
- `uniformBlockName`：指定要查询的统一块的名称，即统一块变量的名称。

**返回值：**
- 如果指定的统一块变量名称有效并且存在于指定的程序对象中，则返回统一块的索引值。
- 如果指定的统一块变量名称无效或不存在于指定的程序对象中，则返回 `GL_INVALID_INDEX`。

**说明：**
`glGetUniformBlockIndex` 函数用于查询指定着色器程序对象中的统一块变量，并返回其索引值。统一块是一种用于管理一组相关联的统一变量的机制，可以将一组统一变量组织成一个统一块，并通过统一块索引来进行操作。

**示例用法：**
```cpp
GLuint program = // 着色器程序对象的名称
const GLchar* uniformBlockName = "MyUniformBlock";
GLuint blockIndex = glGetUniformBlockIndex(program, uniformBlockName);
if (blockIndex != GL_INVALID_INDEX) {
    // 统一块索引有效，可以使用该索引进行后续操作
    // 例如，绑定统一块到绑定点、获取统一块的大小等
} else {
    // 统一块索引无效，可能是指定的统一块名称不存在于指定的程序对象中
}
```

**注意事项：**
- 在调用 `glGetUniformBlockIndex` 函数之前，需要先确保指定的着色器程序对象已经成功链接。
- 确保指定的统一块名称存在于指定的程序对象中，否则将返回 `GL_INVALID_INDEX`。
- 统一块索引是一个整数值，可以用于后续对统一块的操作，例如绑定统一块到绑定点、获取统一块的大小等。