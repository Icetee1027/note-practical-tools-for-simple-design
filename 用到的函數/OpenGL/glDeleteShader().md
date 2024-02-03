
----
`glDeleteShader` 是 [[OpenGL]] 中的函数之一，用于删除指定的着色器对象。着色器对象是编译后的着色器程序的一部分，它们可以是顶点着色器、片段着色器、几何着色器等。当不再需要某个着色器对象时，可以使用 `glDeleteShader` 函数将其删除，释放相关的资源。
### 函数原型
```cpp
void glDeleteShader(GLuint shader);
```
### 参数
- `shader`：要删除的着色器对象的标识符（ID）。
### 返回值
- 无。
### 示例用法
```cpp
GLuint vertexShader = glCreateShader(GL_VERTEX_SHADER);
// 使用 vertexShader 进行着色器编译和操作
// ...

// 在不再需要 vertexShader 时，删除着色器对象
glDeleteShader(vertexShader);
```
### 注意事项
- 使用 `glDeleteShader` 函数后，被删除的着色器对象将不再可用，相关的资源也将被释放。
- 在删除着色器对象之前，需要确保不再需要该着色器对象，以避免资源泄漏和不必要的内存占用。
- 删除着色器对象后，与该对象相关的所有状态和数据都将被释放，因此在调用 `glDeleteShader` 后，不应再使用该着色器对象。