
----
`glGetProgramiv` 是 [[OpenGL]] 中的函数之一，用于查询程序对象的参数值。


### 函数原型
```cpp
void glGetProgramiv(GLuint program, GLenum pname, GLint *params);
```
### 参数
- `program`：要查询的程序对象的标识符（ID）。
- `pname`：要查询的参数名称，可以是以下之一：
  - `GL_DELETE_STATUS`：指示程序对象是否已被标记为删除。
  - `GL_LINK_STATUS`：指示程序对象是否成功连接到当前 [[OpenGL]] 上下文中。
  - `GL_VALIDATE_STATUS`：指示程序对象是否通过验证。
  - `GL_INFO_LOG_LENGTH`：指示程序对象信息日志的长度（包括空字符）。
  - `GL_ATTACHED_SHADERS`：指示程序对象附加的着色器数量。
  - `GL_ACTIVE_ATTRIBUTES`：指示程序对象中活动的属性数量。
  - `GL_ACTIVE_UNIFORMS`：指示程序对象中活动的统一变量数量。
- `params`：指向存储查询结果的变量的指针。
### 返回值
- 无。
### 示例用法
```cpp
GLuint program = // Program object ID
GLint linkStatus;
glGetProgramiv(program, GL_LINK_STATUS, &linkStatus);
if (linkStatus == GL_TRUE) {
    // Program is successfully linked
} else {
    // Program failed to link
}
```
### 注意事项
- `pname` 参数确定要查询的参数类型，而 `params` 参数接收查询结果。
- `glGetProgramiv` 用于获取程序对象的信息，如连接状态、验证状态等。