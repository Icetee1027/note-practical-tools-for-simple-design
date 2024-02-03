
----
`glGetProgramInfoLog` 是 [[OpenGL]] 中用于获取程序对象信息日志的函数之一。它用于检索与程序对象关联的信息日志，该日志包含了编译和连接期间产生的任何警告或错误消息。
### 函数原型
```cpp
void glGetProgramInfoLog(GLuint program, GLsizei maxLength, GLsizei *length, GLchar *infoLog);
```
### 参数
- `program`：要查询信息日志的程序对象标识符。
- `maxLength`：指定存储日志信息的缓冲区最大长度。
- `length`：指向存储实际日志长度的变量的指针。当函数调用后，此变量将包含实际写入缓冲区的日志长度（不包括终止 null 字符）。
- `infoLog`：指向用于存储信息日志的字符数组的指针。
### 返回值
该函数没有返回值。
### 功能
- `glGetProgramInfoLog` 函数用于检索程序对象的信息日志，其中包含了编译和连接期间产生的警告和错误消息。
- 如果日志信息的长度超过了 `maxLength` 所指定的缓冲区长度，则日志将被截断，只返回部分信息。
### 示例用法
```cpp
GLuint program; // 假设已经创建了程序对象并进行了编译和连接

GLchar infoLog[512];
GLsizei length;

glGetProgramInfoLog(program, 512, &length, infoLog);
std::cout << "Program Info Log: " << infoLog << std::endl;
```
上述示例演示了如何使用 `glGetProgramInfoLog` 函数获取程序对象的信息日志，并将其输出到标准输出流。