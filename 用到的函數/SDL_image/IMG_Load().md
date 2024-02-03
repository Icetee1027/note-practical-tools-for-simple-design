
----
`IMG_Load` 是 SDL_image 库中的函数，用于加载图像文件。SDL_image 是一个用于加载不同格式图像文件的扩展库，支持的格式包括 PNG、JPEG、BMP、GIF 等。

### 函数原型
```c
SDL_Surface* IMG_Load(const char* file);
```

### 参数
- `file`：要加载的图像文件的路径字符串。

### 返回值
- 如果加载成功，则返回一个指向 `SDL_Surface` 结构体的指针，该结构体表示加载的图像表面。
- 如果加载失败，则返回 `NULL`，并设置相应的错误信息，可以通过 `IMG_GetError()` 函数获取错误信息。

### 示例用法
```c
SDL_Surface* surface = IMG_Load("image.png");
if (surface == NULL) {
    printf("Failed to load image: %s\n", IMG_GetError());
} else {
    // 使用加载的图像表面进行其他操作
}
```

### 注意事项
- 在使用 `IMG_Load` 加载图像文件之前，需要确保已经初始化了 SDL_image 库。通常在调用 `SDL_Init(SDL_INIT_VIDEO)` 之后，需要调用 `IMG_Init()` 来初始化 SDL_image。
- 加载成功后返回的 `SDL_Surface` 结构体指针需要在不再使用时通过 `SDL_FreeSurface()` 函数释放，以避免内存泄漏。
- SDL_image 支持加载的图像格式取决于编译 SDL_image 时使用的第三方库。