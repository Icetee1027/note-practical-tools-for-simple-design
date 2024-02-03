
----
 `glDeleteBuffers` 函数属于 [[OpenGL]]（OpenGL ES 2.0 及以上版本），用于删除指定数量的缓冲对象。

**函数原型：**
```cpp
void glDeleteBuffers(GLsizei n, const GLuint *buffers);
```

**参数：**
- `n`：要删除的缓冲对象数量。
- `buffers`：指向要删除的缓冲对象名称数组的指针。

**返回值：**
- 无。

**说明：**
`glDeleteBuffers` 函数用于删除指定数量的缓冲对象。参数 `n` 指定了要删除的缓冲对象数量，`buffers` 参数是一个指针，指向要删除的缓冲对象名称数组。

**示例用法：**
```cpp
GLuint buffer1, buffer2;
glGenBuffers(1, &buffer1);
glGenBuffers(1, &buffer2);

// 使用缓冲对象...

// 删除缓冲对象
GLuint buffers[] = { buffer1, buffer2 };
glDeleteBuffers(2, buffers);
```

**注意事项：**
- 调用 `glDeleteBuffers` 函数后，指定的缓冲对象将被标记为删除，并且不能再被使用。