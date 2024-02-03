
----
### 函数介绍

**所属及用途：** `glBufferSubData` 函数属于 [[OpenGL]]，用于更新缓冲对象的数据子集。

**函数原型：**
```cpp
void glBufferSubData(GLenum target, GLintptr offset, GLsizeiptr size, const void* data);
```

**参数：**
- `target`：指定要更新的缓冲对象的类型，可以是 `GL_ARRAY_BUFFER`、`GL_ELEMENT_ARRAY_BUFFER` 等。
- `offset`：指定要更新的缓冲对象中的偏移量，以字节为单位。
- `size`：指定要更新的数据的大小，以字节为单位。
- `data`：指向存储要更新数据的内存块的指针。

**说明：**
`glBufferSubData` 函数用于更新缓冲对象的数据子集。它允许在不重新分配整个缓冲区的情况下，只更新缓冲区中的部分数据。通过指定偏移量和大小，可以指定要更新的数据的范围，并提供要更新的新数据。

**示例用法：**
```cpp
GLuint VBO; // 顶点缓冲对象名称
GLfloat vertices[] = { ... }; // 新顶点数据

glGenBuffers(1, &VBO); // 生成顶点缓冲对象
glBindBuffer(GL_ARRAY_BUFFER, VBO); // 绑定顶点缓冲对象

// 更新顶点缓冲对象的部分数据
glBufferSubData(GL_ARRAY_BUFFER, 0, sizeof(vertices), vertices);
```

**注意事项：**
- `target` 参数指定了要更新的缓冲对象的类型，例如顶点缓冲对象、索引缓冲对象等。
- `offset` 参数指定了要更新数据的起始偏移量，即从缓冲对象中的哪个位置开始更新数据。
- `size` 参数指定了要更新的数据的大小，即更新数据的字节数。
- `data` 参数是一个指针，指向存储要更新数据的内存块，即新数据的起始地址。