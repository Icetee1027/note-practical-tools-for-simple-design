
----
`glEnableVertexAttribArray` 是 [[OpenGL]] 中用于启用指定顶点属性的函数之一。在 [[OpenGL]] 中，顶点属性是指顶点数据中的一个分量，例如顶点的位置、颜色、法线等。

### 函数原型
```cpp
void glEnableVertexAttribArray(GLuint index);
```

### 参数
- `index`：要启用的顶点属性的索引，对应于顶点着色器中的属性位置。

### 返回值
该函数没有返回值。

### 示例用法
```cpp
GLuint VAO;
// 创建或获取顶点数组对象 VAO

// 绑定顶点数组对象 VAO
glBindVertexArray(VAO);

// 启用顶点属性位置为 0 的顶点属性
glEnableVertexAttribArray(0);
```

以上示例代码演示了如何使用 `glEnableVertexAttribArray` 函数启用顶点数组对象中索引为 0 的顶点属性。在启用后，[[OpenGL]] 将使用当前绑定的顶点缓冲对象中的数据来渲染顶点属性。