
-----
### 函数介绍

**所属及用途：** `glTexImage2D` 函数属于 OpenGL（OpenGL ES 1.0 及以上版本），用于指定一个二维纹理图像的像素数据。

**函数原型：**
```cpp
void glTexImage2D(GLenum target, GLint level, GLint internalformat, GLsizei width, GLsizei height, GLint border, GLenum format, GLenum type, const GLvoid * data);
```

**参数：**
- `target`：指定纹理目标，即要设定的纹理类型。可选值包括：
  - `GL_TEXTURE_1D`：一维纹理。
  - `GL_TEXTURE_2D`：二维纹理。
  - `GL_TEXTURE_3D`：三维纹理。
  - `GL_TEXTURE_CUBE_MAP_POSITIVE_X` 等：立方体贴图的各个面。
  - 等等，还有其他纹理类型。
- `level`：指定要设定的纹理级别，通常为 0。
- `internalformat`：指定纹理中的颜色组件的数量和数据类型。可选值包括：
  - `GL_RGBA`：每个像素包含 RGBA 四个分量。
  - `GL_RGB`：每个像素包含 RGB 三个分量。
  - `GL_ALPHA`：每个像素包含一个 Alpha 分量。
  - 等等，还有其他格式。
- `width`：指定纹理图像的宽度（以像素为单位）。
- `height`：指定纹理图像的高度（以像素为单位）。
- `border`：指定边框的宽度。必须为 0。
- `format`：指定像素数据的格式。可选值包括：
  - `GL_RGBA`：每个像素包含 RGBA 四个分量。
  - `GL_RGB`：每个像素包含 RGB 三个分量。
  - `GL_ALPHA`：每个像素包含一个 Alpha 分量。
  - 等等，还有其他格式。
- `type`：指定像素数据的数据类型。可选值包括：
  - `GL_UNSIGNED_BYTE`：每个颜色分量为无符号字节。
  - `GL_UNSIGNED_SHORT_5_6_5`：RGB 分量为 5、6、5 位。
  - `GL_UNSIGNED_SHORT_4_4_4_4`：RGBA 分量为 4、4、4、4 位。
  - 等等，还有其他数据类型。
- `data`：指定包含像素数据的指针。

**返回值：**
- 无。

**说明：**
`glTexImage2D` 函数用于指定一个二维纹理图像的像素数据，将像素数据加载到当前绑定的纹理对象中。这个函数会在当前绑定的纹理对象的指定级别上设置二维纹理图像的像素数据。

**示例用法：**
```cpp
// 将像素数据加载到当前绑定的 2D 纹理对象中
glTexImage2D(GL_TEXTURE_2D, 0, GL_RGBA, width, height, 0, GL_RGBA, GL_UNSIGNED_BYTE, data);
```

**注意事项：**
- 在调用 `glTexImage2D` 函数之前，需要先通过 `glBindTexture` 函数将纹理对象绑定到纹理目标上。
- 纹理图像的像素数据需要事先准备好，并通过 `data` 参数传递给 `glTexImage2D` 函数。
- 确保指定的纹理目标支持当前设置的纹理参数和格式，否则可能会导致渲染错误或未定义的行为。