
----
`glUseProgram` 是 [[OpenGL]] 中的函数之一，用于指定要使用的程序对象。
### 函数原型
```cpp
void glUseProgram(GLuint program);
```
### 参数
- `program`：要使用的程序对象的标识符（ID）。
### 返回值
- 无。
### 示例用法
```cpp
// Assume 'program' is a valid program object
// Use the program object for rendering
glUseProgram(program);
```

### 注意事项
- 调用 `glUseProgram` 将指定当前 OpenGL 上下文中要使用的程序对象。之后的渲染操作将使用该程序对象中的着色器进行处理。
- 如果传入的程序对象标识符是零（0），则表示取消当前使用的程序对象。这将导致 OpenGL 默认使用固定功能管线进行渲染。