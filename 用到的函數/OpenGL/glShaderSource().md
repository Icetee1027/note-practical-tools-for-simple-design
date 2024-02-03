
----
`glShaderSource` 是 [[OpenGL]] 中的函数之一，用于为指定的着色器对象指定源代码。着色器对象是编译后的着色器程序的一部分，它们可以是顶点着色器、片段着色器、几何着色器等。在编译着色器之前，需要使用 `glShaderSource` 函数为着色器对象提供源代码。
### 函数原型
```cpp
void glShaderSource(GLuint shader, GLsizei count, const GLchar **string, const GLint *length);
```
### 参数
- `shader`：要设置源代码的着色器对象的标识符（ID）。
- `count`：指定源代码字符串数组的数量，即传入的源代码字符串的数量。
- `string`：源代码字符串数组的指针，指向要设置的源代码字符串数组。
- `length`：一个整数数组，用于指定每个源代码字符串的长度。如果为 `NULL`，表示每个源代码字符串都是以 null 结尾的 C 字符串。
### 返回值
- 无。
### 示例用法
```cpp
GLuint vertexShader = glCreateShader(GL_VERTEX_SHADER);
const char *vertexShaderSource = "#version 330 core\n"
                                 "layout (location = 0) in vec3 aPos;\n"
                                 "void main()\n"
                                 "{\n"
                                 "    gl_Position = vec4(aPos.x, aPos.y, aPos.z, 1.0);\n"
                                 "}\0";
glShaderSource(vertexShader, 1, &vertexShaderSource, NULL);
```

### 注意事项
- 每个源代码字符串可以包含一个或多个着色器程序的源代码。
- 源代码字符串必须以 null 结尾。
- 在调用 `glCompileShader` 编译着色器之前，必须使用 `glShaderSource` 函数为着色器对象指定源代码。