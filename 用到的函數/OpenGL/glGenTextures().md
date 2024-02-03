
----
 `glGenTextures` 函数属于 [[OpenGL]]（OpenGL ES 1.1 及以上版本），用于生成指定数量的纹理对象。

**函数原型：**
```cpp
void glGenTextures(GLsizei n, GLuint *textures);
```

**参数：**
- `n`：要生成的纹理对象数量。
- `textures`：用于存储生成的纹理对象名称的数组。

**返回值：**
- 无。

**说明：**
`glGenTextures` 函数用于生成指定数量的纹理对象。参数 `n` 指定了要生成的纹理对象数量，`textures` 参数是一个指针，用于存储生成的纹理对象名称。每个生成的纹理对象都有一个唯一的名称，可以在后续的操作中使用该名称引用纹理对象。

**示例用法：**
```cpp
GLuint texture1, texture2;
glGenTextures(1, &texture1);
glGenTextures(1, &texture2);

// 使用纹理对象...

// 删除纹理对象
GLuint textures[] = { texture1, texture2 };
glDeleteTextures(2, textures);
```

**注意事项：**
- 生成的纹理对象名称是无符号整数，可以通过名称引用对应的纹理对象。
- 生成的纹理对象初始状态为空（未定义）的纹理对象，需要通过后续的操作加载纹理数据。