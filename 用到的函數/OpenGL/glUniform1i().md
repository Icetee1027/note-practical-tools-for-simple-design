
----
`glUniform1i` 是一个 OpenGL 函数，用于将整型值设定给指定的 uniform 变量。

### 函数原型
```c
void glUniform1i(GLint location, GLint v0);
```

### 参数
- `location`：要设定值的 uniform 变量的位置索引，可以通过 `glGetUniformLocation` 获取。
- `v0`：要设定给 uniform 变量的整型值。

### 示例用法
```c
GLint textureLoc = glGetUniformLocation(program, "u_texture");
if (textureLoc != -1) {
    glUniform1i(textureLoc, 0); // 将纹理单元索引 0 设定给名为 "u_texture" 的 uniform 变量
} else {
    // Uniform 变量不存在
}
```

在这个示例中，`glUniform1i` 函数被用来将纹理单元索引设定给着色器程序对象中名为 "u_texture" 的 uniform 变量。uniform 变量的位置索引通过 `glGetUniformLocation` 获取，然后使用 `glUniform1i` 来设定其值。