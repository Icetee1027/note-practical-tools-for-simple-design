
-----
### 函数介绍

**所属及用途：** `glTexParameteri` 函数属于 OpenGL（OpenGL ES 1.0 及以上版本），用于设置纹理参数。

**函数原型：**
```cpp
void glTexParameteri(GLenum target, GLenum pname, GLint param);
```

**参数：**
- `target`：指定纹理目标，即要设定的纹理类型。可选值包括：
  - `GL_TEXTURE_1D`：一维纹理。
  - `GL_TEXTURE_2D`：二维纹理。
  - `GL_TEXTURE_3D`：三维纹理。
  - `GL_TEXTURE_CUBE_MAP`：立方体贴图。
  - 等等，还有其他纹理类型。
- `pname`：指定要设置的纹理参数的名称。可选值包括：
  - `GL_TEXTURE_MIN_FILTER`：纹理缩小过滤器。
  - `GL_TEXTURE_MAG_FILTER`：纹理放大过滤器。
  - `GL_TEXTURE_WRAP_S`：纹理 S 轴（水平方向）的环绕模式。
  - `GL_TEXTURE_WRAP_T`：纹理 T 轴（垂直方向）的环绕模式。
  - `GL_TEXTURE_WRAP_R`：纹理 R 轴（深度方向）的环绕模式（对于 3D 纹理）。
  - 等等，还有其他参数名称。
- `param`：指定要设置的纹理参数的值。

**返回值：**
- 无。

**说明：**
`glTexParameteri` 函数用于设置指定纹理对象的参数。根据 `pname` 参数的不同，可以设置纹理的缩小过滤器、放大过滤器以及纹理坐标的环绕模式等。

**示例用法：**
```cpp
// 设置纹理放大过滤器为线性过滤器
glTexParameteri(GL_TEXTURE_2D, GL_TEXTURE_MAG_FILTER, GL_LINEAR);
```

**注意事项：**
- 在调用 `glTexParameteri` 函数之前，需要先通过 `glBindTexture` 函数将纹理对象绑定到纹理目标上。
- 确保指定的纹理参数合法有效，否则可能会导致渲染错误或未定义的行为。