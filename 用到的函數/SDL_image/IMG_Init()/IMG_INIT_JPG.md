
---
`IMG_INIT_JPG` 是 [[SDL_image]] 库中用于初始化 JPG 图像支持的标志之一。

在使用 [[SDL_image]] 加载 JPG 格式的图像之前，需要调用 `IMG_Init()` 函数初始化 [[SDL_image]] 库。而在调用 `IMG_Init()` 函数时，可以传递不同的标志来指定需要初始化的图像支持类型。`IMG_INIT_JPG` 就是其中之一，表示需要初始化 JPG 图像支持。

具体来说，`IMG_INIT_JPG` 标志用于告知 [[SDL_image]] 库需要加载 JPG 图像所需的相关库文件和支持。如果要加载 JPG 格式的图像，就需要在调用 `IMG_Init()` 函数时传递 `IMG_INIT_JPG` 标志，以确保 [[SDL_image]] 正确加载并支持 JPG 图像。

需要注意的是，`IMG_INIT_JPG` 只是初始化 JPG 图像支持的标志之一，[[SDL_image]] 还支持其他格式的图像，例如 PNG、GIF 等，对应的初始化标志也可以传递给 `IMG_Init()` 函数来初始化相应的图像支持。