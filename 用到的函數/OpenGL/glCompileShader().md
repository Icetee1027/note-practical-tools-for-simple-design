
----
`glCompileShader` 是 [[OpenGL]] 中的函数之一，用于编译指定的着色器对象中的源代码。
### 函数原型
```cpp
void glCompileShader(GLuint shader);
```
### 参数
- `shader`：要编译的着色器对象的标识符（ID）。
### 返回值
- 无。
### 示例用法
```cpp
GLuint vertexShader = glCreateShader(GL_VERTEX_SHADER);
// 设置源代码
glShaderSource(vertexShader, 1, &vertexShaderSource, NULL);
// 编译着色器
glCompileShader(vertexShader);
```
### 注意事项
- 在调用 `glCompileShader` 之前，必须使用 `glShaderSource` 函数为着色器对象指定源代码。
- 编译后，可以使用 `glGetShaderiv(shader, GL_COMPILE_STATUS, &success)` 来检查着色器编译是否成功。