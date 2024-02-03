
----
`glGetShaderiv` 是 [[OpenGL]] 中的函数之一，用于查询着色器对象的信息。
### 函数原型
```cpp
void glGetShaderiv(GLuint shader, GLenum pname, GLint *params);
```
### 参数
- `shader`：要查询的着色器对象的标识符（ID）。
- `pname`：要查询的参数名称，可以是以下之一：
  - `GL_SHADER_TYPE`：着色器类型。
  - `GL_DELETE_STATUS`：删除状态，如果着色器已被标记为删除，则返回 `GL_TRUE`。
  - `GL_COMPILE_STATUS`：编译状态，如果着色器已成功编译，则返回 `GL_TRUE`。
  - `GL_INFO_LOG_LENGTH`：信息日志的长度。
  - 其他着色器特定的参数，如 `GL_SHADER_SOURCE_LENGTH`。
- `params`：用于存储查询结果的变量。
### 返回值
- 无。
### 示例用法
```cpp
GLuint vertexShader = glCreateShader(GL_VERTEX_SHADER);
// 设置源代码
glShaderSource(vertexShader, 1, &vertexShaderSource, NULL);
// 编译着色器
glCompileShader(vertexShader);

GLint success;
// 查询编译状态
glGetShaderiv(vertexShader, GL_COMPILE_STATUS, &success);
if (!success) {
    GLint logLength;
    // 获取信息日志的长度
    glGetShaderiv(vertexShader, GL_INFO_LOG_LENGTH, &logLength);
    if (logLength > 0) {
        std::vector<GLchar> errorLog(logLength + 1);
        // 获取信息日志
        glGetShaderInfoLog(vertexShader, logLength, NULL, &errorLog[0]);
        std::cout << "Shader compilation failed:\n" << &errorLog[0] << std::endl;
    }
}
```
### 注意事项
- `glGetShaderiv` 用于查询着色器对象的状态信息，例如编译状态、信息日志长度等。