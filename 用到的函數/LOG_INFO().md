
----
這段程式碼位於 `Context` 類的建構函式中，它的作用是初始化[[OpenGL]]上下文並輸出[[OpenGL]]相關的資訊到日誌中。現在讓我們來再次推測這些程式碼中每個 `LOG_INFO` 的用途：

1. `LOG_INFO("OpenGL Info");`
   - 這行程式碼的作用是將一條訊息 `"OpenGL Info"` 輸出到日誌中，用來標識接下來輸出的是OpenGL相關的資訊。

2. `LOG_INFO("  Vendor: {}", glGetString(GL_VENDOR));`
   - 這行程式碼的作用是獲取並輸出OpenGL的廠商資訊到日誌中，`glGetString(GL_VENDOR)` 用於獲取OpenGL的廠商資訊。

3. `LOG_INFO("  Renderer: {}", glGetString(GL_RENDERER));`
   - 這行程式碼的作用是獲取並輸出OpenGL的渲染器資訊到日誌中，`glGetString(GL_RENDERER)` 用於獲取OpenGL的渲染器資訊。

4. `LOG_INFO("  Version: {}", glGetString(GL_VERSION));`
   - 這行程式碼的作用是獲取並輸出OpenGL的版本資訊到日誌中，`glGetString(GL_VERSION)` 用於獲取OpenGL的版本資訊。

5. `LOG_INFO("  GLSL Version: {}", glGetString(GL_SHADING_LANGUAGE_VERSION));`
   - 這行程式碼的作用是獲取並輸出OpenGL Shading Language（GLSL）的版本資訊到日誌中，`glGetString(GL_SHADING_LANGUAGE_VERSION)` 用於獲取GLSL的版本資訊。

總的來說，這些 `LOG_INFO` 的作用是將初始化後的OpenGL相關資訊輸出到日誌中，以便後續的偵錯和追蹤程式執行流程。