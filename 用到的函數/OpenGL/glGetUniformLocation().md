
----
`glGetUniformLocation` 是一个 OpenGL 函数，用于获取着色器程序对象中指定 uniform 变量的位置。

### 函数原型
```c
GLint glGetUniformLocation(GLuint program, const GLchar *name);
```

### 参数
- `program`：要查询的着色器程序对象的标识符。
- `name`：要获取其位置的 uniform 变量的名称。

### 返回值
- 如果 uniform 变量存在于指定的着色器程序对象中，则返回该 uniform 变量的位置索引；否则返回 -1。

### 示例用法
```c
GLuint program = glCreateProgram();
// Attach shaders, link program, etc...

GLint positionLoc = glGetUniformLocation(program, "u_position");
if (positionLoc != -1) {
    // Uniform variable exists in the shader program
    // Use its location for setting its value
} else {
    // Uniform variable not found in the shader program
}
```

在这个示例中，`glGetUniformLocation` 函数被用来获取着色器程序对象中名为 `u_position` 的 uniform 变量的位置索引。如果该 uniform 变量存在于着色器程序对象中，则可以使用返回的位置索引来设置其值；否则将返回 -1，表示该 uniform 变量不存在。