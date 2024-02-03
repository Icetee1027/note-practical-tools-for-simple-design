
----
### 函数介绍

**所属及用途：** `glBindTexture` 函数属于 OpenGL（OpenGL ES 1.0 及以上版本），用于绑定一个纹理对象到当前活动的纹理单元。

**函数原型：**
```cpp
void glBindTexture(GLenum target, GLuint texture);
```

**参数：**
- `target`：指定纹理目标，即要绑定的纹理类型。可选值包括：
  - `GL_TEXTURE_1D`：一维纹理。
  - `GL_TEXTURE_2D`：二维纹理。
  - `GL_TEXTURE_3D`：三维纹理。
  - `GL_TEXTURE_CUBE_MAP`：立方体贴图。
  - 等等，还有其他纹理类型。
- `texture`：指定要绑定的纹理对象的名称（ID），即纹理的标识符。

**返回值：**
- 无。

**说明：**
`glBindTexture` 函数将指定的纹理对象绑定到当前活动的纹理单元。纹理单元通过调用 `glActiveTexture` 函数设置。绑定纹理后，后续的纹理操作（如设置纹理参数、加载纹理图像等）将作用于当前活动的纹理单元上。

**示例用法：**
```cpp
// 绑定纹理对象到当前活动的纹理单元上
glBindTexture(GL_TEXTURE_2D, textureID);
```

**注意事项：**
- 在进行纹理绑定之前，需要先通过 `glGenTextures` 函数生成纹理对象，并通过其他函数加载纹理数据到纹理对象中。
- 当纹理目标为 `GL_TEXTURE_CUBE_MAP` 时，需要通过 `glTexImage2D` 或 `glTexImage3D` 函数为每个立方体贴图面加载纹理数据。
- 在进行纹理绑定后，需要根据需要进行相应的纹理参数设置、纹理过滤器设置等操作，以确保正确的纹理渲染效果。