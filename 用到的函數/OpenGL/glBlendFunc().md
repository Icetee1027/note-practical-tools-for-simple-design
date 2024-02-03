  
---
`glBlendFunc()` 是 [[OpenGL]] 中用于设置混合函数的函数之一。在绘制透明或半透明对象时，混合函数决定了新像素颜色和已存储在帧缓冲区中的像素颜色如何混合。
具体来说，`glBlendFunc()` 函数用于指定源颜色和目标颜色的混合因子，以及混合运算的方式。它的原型如下：
```cpp

void glBlendFunc(GLenum sfactor, GLenum dfactor);

```
参数 `sfactor` 和 `dfactor` 分别表示源颜色因子和目标颜色因子。它们可以是以下常量之一：
- `GL_ZERO`：表示因子为 0。
- `GL_ONE`：表示因子为 1。
- `GL_SRC_COLOR`：表示使用源颜色的颜色值。
- `GL_ONE_MINUS_SRC_COLOR`：表示使用 1 减去源颜色的颜色值。
- `GL_DST_COLOR`：表示使用目标颜色的颜色值。
- `GL_ONE_MINUS_DST_COLOR`：表示使用 1 减去目标颜色的颜色值。
- [[GL_SRC_ALPHA]]：表示使用源颜色的 alpha 值。
- [[GL_ONE_MINUS_SRC_ALPHA]]：表示使用 1 减去源颜色的 alpha 值。
- `GL_DST_ALPHA`：表示使用目标颜色的 alpha 值。
- `GL_ONE_MINUS_DST_ALPHA`：表示使用 1 减去目标颜色的 alpha 值。
- `GL_CONSTANT_COLOR`：表示使用常量颜色值。
- `GL_ONE_MINUS_CONSTANT_COLOR`：表示使用 1 减去常量颜色值。
- `GL_CONSTANT_ALPHA`：表示使用常量 alpha 值。
- `GL_ONE_MINUS_CONSTANT_ALPHA`：表示使用 1 减去常量 alpha 值。
`glBlendFunc()` 设置的混合函数将影响到之后所有的绘制操作，直到下一次调用 `glBlendFunc()`。常见的混合函数包括：

- `glBlendFunc(GL_SRC_ALPHA, GL_ONE_MINUS_SRC_ALPHA)`：常用于绘制半透明对象，根据源像素的 alpha 值对颜色进行混合。
- `glBlendFunc(GL_ONE, GL_ONE)`：常用于实现加法混合，将源像素颜色和目标像素颜色相加。

示例用法：
```cpp
glBlendFunc(GL_SRC_ALPHA, GL_ONE_MINUS_SRC_ALPHA); // 设置源颜色使用源 alpha 值，目标颜色使用 1 减去源 alpha 值
glEnable(GL_BLEND); // 启用颜色混合功能
```