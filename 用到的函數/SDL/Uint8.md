
----
`Uint8` 是 SDL 库中定义的无符号 8 位整数类型。它通常用于表示颜色分量、像素值等需要在 0 到 255 范围内取值的情况。

在 SDL 库中，`Uint8` 的定义通常如下所示：
```c
typedef uint8_t Uint8;
```
这里的 `uint8_t` 是 C 标准库 `<stdint.h>` 中定义的无符号 8 位整数类型。

### 示例用法
```c
Uint8 red = 255;    // 红色分量的最大值
Uint8 green = 128;  // 绿色分量的中间值
Uint8 blue = 0;     // 蓝色分量的最小值

// 使用 SDL_CreateRGBSurface 创建一个表面，并将颜色填充为白色
SDL_Surface* surface = SDL_CreateRGBSurface(0, 100, 100, 32, 0, 0, 0, 0);
SDL_FillRect(surface, NULL, SDL_MapRGB(surface->format, red, green, blue));
```

在这个示例中，`Uint8` 被用来表示颜色分量的值，从而创建了一个 RGB 色彩模式的表面，并填充为特定颜色。