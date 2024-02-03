[SDL2_image/FrontPage - SDL Wiki (libsdl.org)](https://wiki.libsdl.org/SDL2_image/FrontPage)

---
SDL_image 是一个用于加载和处理图像文件的扩展库，通常与 SDL 库一起使用。它支持多种图像格式，包括 BMP、GIF、JPEG、PNG、TIFF 等，并提供了一系列函数用于加载和处理这些图像文件，使开发者能够轻松地在 SDL 应用程序中加载和显示图像。
**常用功能：**
1. **加载图像文件：**
   - `IMG_Load()`：加载图像文件，返回一个 SDL_Surface 对象。
2. **保存图像文件：**
   - `IMG_SavePNG()`：保存图像为 PNG 格式。
   - `IMG_SaveJPG()`：保存图像为 JPEG 格式。
3. **图像格式支持：**
   - [[IMG_Init()]]：初始化 SDL_image 库，指定支持的图像格式。
   - [[IMG_Quit()]]：关闭 SDL_image 库。
4. **获取图像信息：**
   - `IMG_GetError()`：获取错误信息。
SDL_image 提供了简单易用的 API，使得在 SDL 应用程序中加载和处理图像变得容易。开发者可以使用 SDL_image 加载各种图像格式的文件，并将其显示在 SDL 窗口中，如游戏中的角色、背景、UI 图元等。