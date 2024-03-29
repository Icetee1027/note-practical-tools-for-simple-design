- [[vec2]]

----
這段程式碼定義了名為 `Transform` 的結構，位於 `Util` 命名空間中。這個結構用於表示2D圖形的變換，包括平移、旋轉和縮放。結構包含三個成員變數：

- **`translation`**：用於表示平移的二維向量，預設為原點 `{0, 0}`。此向量指定了物體在二維空間中沿著 X 和 Y 軸的移動量。

- **`rotation`**：用於表示旋轉的浮點數，預設為 0。表示物體繞著 Z 軸的旋轉角度，以弧度為單位。

- **`scale`**：用於表示縮放的二維向量，預設為 `{1, 1}`。此向量指定了物體在 X 和 Y 軸上的縮放比例。

這個結構提供了一種方便的方式來描述2D圖形的基本變換，例如平移、旋轉和縮放。它是一個輕量級的結構，只包含了必要的成員變數，可以方便地傳遞給圖形渲染函式，以應用相應的變換。

此外，這個結構使用了[[GLM]]（OpenGL Mathematics）庫提供的數學類型和函式，包括 `glm::vec2` 和相關的數學運算函式，以便在程式中進行向量計算和變換矩陣的構建。