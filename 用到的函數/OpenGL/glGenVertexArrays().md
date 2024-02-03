
----
`glGenVertexArrays` 是 [[OpenGL]] 中用于生成顶点数组对象（Vertex Array Object，VAO）的函数之一。顶点数组对象是 [[OpenGL]] 中一种重要的对象，用于存储顶点数据的配置信息，包括顶点属性指针、顶点缓冲对象等。

### 函数原型
```cpp
void glGenVertexArrays(GLsizei n, GLuint *arrays);
```

### 参数
- `n`：要生成的顶点数组对象的数量。
- `arrays`：用于存储生成的顶点数组对象的数组。

### 返回值
该函数没有返回值。

### 示例用法
```cpp
GLuint VAO;
glGenVertexArrays(1, &VAO);
```

以上示例代码演示了如何使用 `glGenVertexArrays` 函数生成一个顶点数组对象，并将其存储在名为 `VAO` 的变量中。

在使用顶点数组对象之前，通常还需要调用 `glBindVertexArray` 函数绑定顶点数组对象，以便后续操作能够对该对象进行配置和使用。