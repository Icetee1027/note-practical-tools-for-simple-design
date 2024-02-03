
----
 `glDeleteTextures` 函数属于 [[OpenGL]]（OpenGL ES 1.1 及以上版本），用于删除指定数量的纹理对象。

**函数原型：**
```cpp
void glDeleteTextures(GLsizei n, const GLuint *textures);
```

**参数：**
- `n`：要删除的纹理对象数量。
- `textures`：要删除的纹理对象名称数组的指针。

**返回值：**
- 无。

**说明：**
`glDeleteTextures` 函数用于删除指定数量的纹理对象。参数 `n` 指定了要删除的纹理对象数量，`textures` 参数是一个指向存储要删除的纹理对象名称的数组的指针。通过调用该函数，可以释放纹理对象所占用的内存，并标记这些纹理对象为删除状态。被标记为删除状态的纹理对象将在稍后的时间被销毁。

**示例用法：**
```cpp
GLuint texture1, texture2;
// 创建纹理对象 texture1 和 texture2

// 删除纹理对象
GLuint textures[] = { texture1, texture2 };
glDeleteTextures(2, textures);
```

**注意事项：**
- 被删除的纹理对象在调用 `glDeleteTextures` 函数后不会立即销毁，而是被标记为删除状态。[[OpenGL]] 会在适当的时机（例如调用 `glFlush`、`glFinish` 或上下文销毁时）销毁这些纹理对象。
- 在调用 `glDeleteTextures` 后，应将纹理对象的名称设置为 0 或无效值，以避免在后续使用中出现错误。