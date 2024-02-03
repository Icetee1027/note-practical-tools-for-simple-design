
----
`glAttachShader` 是 [[OpenGL]] 中的函数之一，用于将着色器附加到程序对象上。
### 函数原型
```cpp
void glAttachShader(GLuint program, GLuint shader);
```
### 参数
- `program`：要附加着色器的程序对象的标识符（ID）。
- `shader`：要附加的着色器对象的标识符（ID）。
### 返回值
- 无。
### 示例用法
```cpp
GLuint program = glCreateProgram();
GLuint vertexShader = glCreateShader(GL_VERTEX_SHADER);
GLuint fragmentShader = glCreateShader(GL_FRAGMENT_SHADER);

// Attach shaders to the program
glAttachShader(program, vertexShader);
glAttachShader(program, fragmentShader);

// Link the program after attaching shaders
glLinkProgram(program);
```

### 注意事项
- 在使用 `glLinkProgram` 函数链接程序对象之前，必须先将着色器附加到程序对象上。
- 附加着色器后，不会立即生效，程序需要链接后才能生效。