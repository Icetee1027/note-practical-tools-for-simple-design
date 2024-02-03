
----
`glDrawElements` 是 [[OpenGL]] 中用于绘制索引化几何图元的函数之一。

### 函数原型

```cpp
void glDrawElements(GLenum mode, GLsizei count, GLenum type, const GLvoid * indices);
```

### 参数

- `mode`：指定要绘制的图元类型，可以是以下常量之一：
  - `GL_POINTS`
  - `GL_LINES`
  - `GL_LINE_STRIP`
  - `GL_LINE_LOOP`
  - `GL_TRIANGLES`
  - `GL_TRIANGLE_STRIP`
  - `GL_TRIANGLE_FAN`
  - 等等。

- `count`：指定要绘制的顶点数量。

- `type`：指定索引数据的类型，可以是以下常量之一：
  - `GL_UNSIGNED_BYTE`
  - `GL_UNSIGNED_SHORT`
  - `GL_UNSIGNED_INT`

- `indices`：指定一个指针，指向索引数据的起始位置。

### 返回值

`void`

### 说明

`glDrawElements` 根据索引数组中的索引顺序，绘制一系列图元。图元的顶点从索引数组中获取，并根据 mode 参数指定的绘制模式组合成图元。每个索引会从当前绑定的顶点数组对象的索引缓冲中获取对应的顶点数据。

### 示例用法

```cpp
// 绘制一个三角形
glBindVertexArray(VAO); // 绑定顶点数组对象
glDrawElements(GL_TRIANGLES, 3, GL_UNSIGNED_INT, 0);
```

以上示例代码绘制了一个三角形，顶点数据存储在当前绑定的顶点数组对象中，索引数据存储在当前绑定的索引缓冲中。