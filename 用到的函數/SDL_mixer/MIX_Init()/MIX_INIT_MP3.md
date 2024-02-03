
---
`MIX_INIT_MP3` 是 [[SDL_mixer]] 库中用于初始化 MP3 音频支持的标志之一。

在使用 [[SDL_mixer]] 播放 MP3 格式的音频之前，需要调用 `Mix_Init()` 函数初始化 [[SDL_mixer]] 库。而在调用 `Mix_Init()` 函数时，可以传递不同的标志来指定需要初始化的音频支持类型。`MIX_INIT_MP3` 就是其中之一，表示需要初始化 MP3 音频支持。

具体来说，`MIX_INIT_MP3` 标志用于告知 [[SDL_mixer]] 库需要加载 MP3 音频所需的相关库文件和支持。如果要播放 MP3 格式的音频，就需要在调用 `Mix_Init()` 函数时传递 `MIX_INIT_MP3` 标志，以确保 [[SDL_mixer]] 正确加载并支持 MP3 音频。

需要注意的是，`MIX_INIT_MP3` 只是初始化 MP3 音频支持的标志之一，[[SDL_mixer]] 还支持其他格式的音频，例如 WAV、OGG 等，对应的初始化标志也可以传递给 `Mix_Init()` 函数来初始化相应的音频支持。