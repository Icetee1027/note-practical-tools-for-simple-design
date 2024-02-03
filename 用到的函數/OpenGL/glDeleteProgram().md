
----
`glDeleteProgram` 是 [[OpenGL]] 中的函数之一，用于删除一个程序对象。
### 函数原型
```cpp
void glDeleteProgram(GLuint program);
```
### 参数
- `program`：要删除的程序对象的标识符（ID）。
### 返回值
- 无。
### 示例用法
```cpp
// Assume 'program' is a valid program object
// Delete the program object
glDeleteProgram(program);
```
### 注意事项
- 调用 `glDeleteProgram` 后，指定的程序对象及其相关资源将被销毁，包括链接的着色器、Uniform 变量和着色器变量等。
- 如果程序对象正在当前 [[OpenGL]] 上下文中使用，那么它将被标记为删除，但实际上并不会立即被销毁。只有当它不再被任何程序对象使用时，才会被真正删除。
- 删除程序对象后，相关联的着色器不会自动删除。需要单独调用 `glDeleteShader` 来删除它们。