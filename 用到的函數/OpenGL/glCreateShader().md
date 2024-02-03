
----
`glCreateShader()` 是 [[OpenGL]] 中用于创建着色器对象的函数之一。着色器对象是 [[OpenGL]] 中用来管理着色器代码的对象，它可以表示顶点着色器、片段着色器或其他类型的着色器。

### 函数签名
```cpp
GLuint glCreateShader(GLenum shaderType);
```

### 参数
- `shaderType`：枚举值，指定要创建的着色器对象的类型。可以是以下值之一：
  - `GL_VERTEX_SHADER`：顶点着色器
  - `GL_FRAGMENT_SHADER`：片段着色器
  - 其他可能的着色器类型，如几何着色器、计算着色器等

### 返回值
- 返回一个无符号整数 (GLuint)，表示新创建的着色器对象的标识符。

### 函数说明
- `glCreateShader()` 函数创建一个空的着色器对象，并返回其标识符。
- 着色器对象用于存储编写的着色器代码，并通过编译将其转换为可执行的 GPU 代码。
- 创建的着色器对象还没有包含任何代码，需要通过 `glShaderSource()` 函数加载着色器代码，并使用 `glCompileShader()` 函数编译它们。

### 示例用法
```cpp
// 创建一个顶点着色器对象
GLuint vertexShader = glCreateShader(GL_VERTEX_SHADER);
// 检查是否成功创建着色器对象
if (vertexShader == 0) {
    // 顶点着色器对象创建失败
    // 处理错误
} else {
    // 顶点着色器对象创建成功
    // 可以继续加载着色器代码、编译着色器等操作
}
```

### 注意事项
- 在使用完着色器对象后，需要使用 `glDeleteShader()` 函数来删除它，以释放资源。

`glCreateShader()` 函数是创建着色器对象的第一步，用于初始化一个空的着色器对象，后续需要加载着色器代码并编译它才能将着色器转换为可执行的 GPU 代码。