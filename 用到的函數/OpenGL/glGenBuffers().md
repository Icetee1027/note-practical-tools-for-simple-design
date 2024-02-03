
----
`glGenBuffers` 是 [[OpenGL]] 中用于生成缓冲对象的函数之一。

### 函数原型

```cpp
void glGenBuffers(GLsizei n, GLuint *buffers);
```

### 参数

- `n`：要生成的缓冲对象的数量。

- `buffers`：一个 GLuint 类型的数组，用于存储生成的缓冲对象的名称。

### 返回值

`void`

### 说明

`glGenBuffers` 用于生成指定数量的缓冲对象，并将它们的名称存储在指定的数组中。这些缓冲对象可以用于存储顶点数据、索引数据、纹理数据等。

### 示例用法

```cpp
GLuint VBO;
glGenBuffers(1, &VBO); // 生成一个顶点缓冲对象
```

以上示例代码生成了一个顶点缓冲对象，并将其名称存储在变量 VBO 中。