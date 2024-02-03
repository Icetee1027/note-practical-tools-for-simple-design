[SDL2_ttf/FrontPage - SDL Wiki (libsdl.org)](https://wiki.libsdl.org/SDL2_ttf/FrontPage)

---
SDL_ttf 是用于在 SDL 应用程序中加载和渲染 TrueType 字体的库。它提供了一系列函数，用于处理 TrueType 字体文件，实现在 SDL 窗口中显示各种样式和格式的文本内容。
**常用功能：**
1. **加载字体文件：**
   - `TTF_OpenFont()`：加载 TrueType 字体文件，创建字体对象。
   - `TTF_OpenFontIndex()`：加载 TrueType 字体文件的指定字体索引，创建字体对象。
2. **渲染文本：**
   - `TTF_RenderText_Solid()`：将文本渲染到表面上，使用单一颜色填充。
   - `TTF_RenderText_Shaded()`：将文本渲染到表面上，使用渐变填充。
   - `TTF_RenderText_Blended()`：将文本渲染到表面上，使用抗锯齿技术填充。
3. **获取文本尺寸：**
   - `TTF_SizeText()`：获取指定文本在指定字体下的宽度和高度。
4. **设置字体样式：**
   - `TTF_SetFontStyle()`：设置字体的样式，如粗体、斜体、下划线等。
5. **释放资源：**
   - `TTF_CloseFont()`：释放字体对象的资源。
**重要函数：**
- [[TTF_Init()]]：初始化 TrueType 字体支持。通常在初始化 SDL 库后调用，确保 SDL_ttf 库能够正常加载和渲染 TrueType 字体。
- [[TTF_Quit()]]：关闭 TrueType 字体支持。释放 SDL_ttf 库所占用的资源。
除了上述常用和重要函数外，SDL_ttf 还提供了其他一些函数，用于设置字体的属性、获取字体信息等。使用 SDL_ttf 库可以方便地在 SDL 应用程序中实现文本渲染功能，例如在游戏界面、用户界面、文本编辑器等场景中显示文本内容。