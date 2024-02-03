
----
`glDetachShader` 是 [[OpenGL]] 中的函数之一，用于将着色器从程序对象中分离。
### 函数原型
```cpp
void glDetachShader(GLuint program, GLuint shader);
```
### 参数
- `program`：要从中分离着色器的程序对象的标识符（ID）。
- `shader`：要分离的着色器对象的标识符（ID）。
### 返回值
- 无。
### 示例用法
```cpp
// Assume 'program' is a valid program object and 'shader' is a valid shader object
// Detach shader from the program
glDetachShader(program, shader);
```
### 注意事项
- 分离着色器后，它不会立即被删除，而是保留在程序对象中，直到程序对象被删除或重新链接。
- 分离着色器后，程序对象不再与该着色器相关联。