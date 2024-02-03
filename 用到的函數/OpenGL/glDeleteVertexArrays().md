
----
`glDeleteVertexArrays` 是 [[OpenGL]] 中用于删除顶点数组对象（Vertex Array Object，VAO）的函数之一。顶点数组对象是 [[OpenGL]] 中一种重要的对象，用于存储顶点数据的配置信息，包括顶点属性指针、顶点缓冲对象等。

### 函数原型
```cpp
void glDeleteVertexArrays(GLsizei n, const GLuint *arrays);
```

### 参数
- `n`：要删除的顶点数组对象的数量。
- `arrays`：指向要删除的顶点数组对象的数组。

### 返回值
该函数没有返回值。

### 示例用法
```cpp
GLuint VAO;
// 创建或获取顶点数组对象 VAO

// 删除顶点数组对象 VAO
glDeleteVertexArrays(1, &VAO);
```

以上示例代码演示了如何使用 `glDeleteVertexArrays` 函数删除一个顶点数组对象。

在删除顶点数组对象之后，相应的顶点数组对象将不再可用，并且相关资源会被释放。