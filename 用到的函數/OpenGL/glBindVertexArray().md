
----
`glBindVertexArray` 是 [[OpenGL]] 中用于绑定顶点数组对象（Vertex Array Object，VAO）的函数之一。顶点数组对象是 OpenGL 中一种重要的对象，用于存储顶点数据的配置信息，包括顶点属性指针、顶点缓冲对象等。

### 函数原型
```cpp
void glBindVertexArray(GLuint array);
```

### 参数
- `array`：要绑定的顶点数组对象的标识符。

### 返回值
该函数没有返回值。

### 示例用法
```cpp
GLuint VAO;
// 创建或获取顶点数组对象 VAO

// 绑定顶点数组对象 VAO
glBindVertexArray(VAO);
```

以上示例代码演示了如何使用 `glBindVertexArray` 函数绑定一个顶点数组对象。

在绑定顶点数组对象之后，后续的顶点属性配置和渲染调用都将作用于该顶点数组对象。