
-----
`SDL_FreeSurface` 是 SDL 库中用于释放表面（surface）内存的函数。表面是 SDL 中用于存储图像数据的数据结构，使用 `SDL_CreateRGBSurface` 等函数创建。当不再需要某个表面时，应该调用 `SDL_FreeSurface` 来释放其内存，以避免内存泄漏。
### 函数原型

```c
void SDL_FreeSurface(SDL_Surface* surface);
```
### 参数
- `surface`：要释放内存的表面对象，是一个指向 `SDL_Surface` 结构体的指针。
### 注意事项

- 调用 `SDL_FreeSurface` 后，表面对象及其所占用的内存将被释放。
- 调用此函数后，应该确保不再对已释放的表面对象进行访问，否则会导致未定义的行为。
- 如果表面是由 `SDL_CreateRGBSurface`、`SDL_CreateRGBSurfaceWithFormat` 等函数创建的，则应该使用 `SDL_FreeSurface` 来释放其内存。
- 如果表面是作为纹理渲染目标创建的，则不需要调用 `SDL_FreeSurface` 来释放其内存，而是应该使用 `SDL_DestroyTexture` 函数来销毁纹理。

### 示例用法

```c
#include <SDL.h>

// 创建表面
SDL_Surface* surface = SDL_CreateRGBSurface(0, 640, 480, 32, 0, 0, 0, 0);
if (surface == NULL) {
    // 处理表面创建失败的情况
}

// 使用表面...

// 释放表面内存
SDL_FreeSurface(surface);
```

以上示例演示了如何使用 `SDL_FreeSurface` 函数释放由 `SDL_CreateRGBSurface` 创建的表面内存。