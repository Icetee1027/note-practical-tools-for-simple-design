
----
`glVertexAttribPointer` 是 OpenGL 中用于设置顶点属性指针的函数之一。它指定了顶点数组中每个顶点属性的数据格式和位置。

### 函数原型
```cpp
void glVertexAttribPointer(GLuint index, GLint size, GLenum type, GLboolean normalized, GLsizei stride, const GLvoid *pointer);
```

### 参数
- `index`：指定要修改的顶点属性的索引。
- `size`：指定顶点属性的组件数量。可以是 1、2、3 或 4。
- `type`：指定顶点属性的数据类型。可以是 `GL_BYTE`、`GL_UNSIGNED_BYTE`、`GL_SHORT`、`GL_UNSIGNED_SHORT`、`GL_INT`、`GL_UNSIGNED_INT`、`GL_FLOAT`、`GL_DOUBLE` 等。
- `normalized`：指定是否应该将非浮点类型的数据映射到区间 [0, 1] 或 [-1, 1]。如果设置为 `GL_TRUE`，则数据会被归一化；如果设置为 `GL_FALSE`，则数据不会被归一化。
- `stride`：指定相邻顶点属性之间的字节偏移量。如果设置为 0，则表示顶点属性是紧密打包的（即相邻顶点属性之间没有间隔）。
- `pointer`：指定顶点属性数组的指针。如果设置为 `nullptr`，则表示顶点属性数据存储在当前绑定的顶点缓冲对象中；否则，表示顶点属性数据存储在 CPU 内存中的某个位置。

### 返回值
该函数没有返回值。

### 示例用法
```cpp
GLuint VBO;
// 创建或获取顶点缓冲对象 VBO

// 绑定顶点缓冲对象 VBO
glBindBuffer(GL_ARRAY_BUFFER, VBO);

// 启用顶点属性位置为 0 的顶点属性
glEnableVertexAttribArray(0);

// 指定顶点属性位置为 0 的数据格式和位置
glVertexAttribPointer(0, 3, GL_FLOAT, GL_FALSE, 3 * sizeof(GLfloat), (GLvoid*)0);
```

以上示例代码演示了如何使用 `glVertexAttribPointer` 函数指定顶点缓冲对象中索引为 0 的顶点属性的数据格式和位置。在此示例中，顶点属性位置为 0，数据类型为 `GL_FLOAT`，每个顶点属性包含 3 个浮点数，相邻顶点属性之间的字节偏移量为 3 个浮点数大小。