
----
`glGetShaderInfoLog` 是 [[OpenGL]] 中的函数之一，用于获取着色器对象的信息日志。
### 函数原型
```cpp
void glGetShaderInfoLog(GLuint shader, GLsizei maxLength, GLsizei *length, GLchar *infoLog);
```
### 参数
- `shader`：要获取信息日志的着色器对象的标识符（ID）。
- `maxLength`：infoLog 缓冲区的最大长度。
- `length`：用于存储实际写入 infoLog 的字符数量，可为 nullptr。
- `infoLog`：用于存储信息日志的缓冲区。
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
- `glGetShaderInfoLog` 用于获取着色器对象的信息日志，通常用于查看编译错误和警告信息。