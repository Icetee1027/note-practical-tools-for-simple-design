
----
`glBufferData` 函数属于 [[OpenGL]]（OpenGL ES 2.0 及以上版本），用于向当前绑定的缓冲对象中传输数据。

**函数原型：**
```cpp
void glBufferData(GLenum target, GLsizeiptr size, const GLvoid *data, GLenum usage);
```

**参数：**
- `target`：指定绑定点目标，表示缓冲对象的类型，可以是以下值之一：
  - `GL_ARRAY_BUFFER`：用于存储顶点属性数据。
  - `GL_ELEMENT_ARRAY_BUFFER`：用于存储索引数据。
  - 其他 OpenGL 相关类型。
- `size`：要传输数据的字节数。
- `data`：指向要传输数据的指针。
- `usage`：指定数据的使用方式，可以是以下值之一：
  - `GL_STATIC_DRAW`：数据不会或几乎不会改变。
  - `GL_DYNAMIC_DRAW`：数据会被改变但不频繁。
  - `GL_STREAM_DRAW`：数据会频繁改变。

**返回值：**
- 无。

**说明：**
`glBufferData` 函数用于向当前绑定的缓冲对象中传输数据。传输的数据由 `data` 参数指定，数据的大小由 `size` 参数指定。`usage` 参数指定了数据的使用方式，[[OpenGL]] 根据这个参数来优化内存存储和访问模式。

**示例用法：**
```cpp
GLuint buffer;
glGenBuffers(1, &buffer); // 生成一个缓冲对象名称

// 将缓冲对象绑定到 GL_ARRAY_BUFFER 目标上
glBindBuffer(GL_ARRAY_BUFFER, buffer);

// 定义顶点数据
GLfloat vertices[] = {
    0.0f,  0.5f, 0.0f,
    0.5f, -0.5f, 0.0f,
   -0.5f, -0.5f, 0.0f
};

// 将顶点数据传输到当前绑定的缓冲对象中
glBufferData(GL_ARRAY_BUFFER, sizeof(vertices), vertices, GL_STATIC_DRAW);
```

**注意事项：**
- 在调用 `glBufferData` 之前，需要确保已经将缓冲对象绑定到了目标上。
- 传输的数据大小由 `size` 参数指定，应与实际数据大小相匹配，否则会导致未定义的行为。