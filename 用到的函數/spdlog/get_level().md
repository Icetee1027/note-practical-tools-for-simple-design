
----
`get_level` 是 `spdlog` 函式庫中的一個函式，用於獲取當前的全局日誌級別。`spdlog` 是一個用於 C++ 的快速、靈活和易於使用的日誌庫，提供了豐富的功能來記錄和管理應用程序的日誌消息。
### 函式簽名
```cpp
spdlog::level::level_enum spdlog::get_level();
```
### 返回值
- 當前的全局日誌級別，是 `spdlog::level::level_enum` 列舉類型的一個值，包括 `trace`、`debug`、`info`、`warn`、`err` 和 `critical`。
### 功能
該函式允許你獲取當前的全局日誌級別，以便進行後續的判斷和處理。你可以根據當前的日誌級別來採取相應的行動，例如根據不同的級別來執行不同的日誌輸出設置。
### 示例用法
```cpp
spdlog::level::level_enum current_level = spdlog::get_level();
```
上面的示例代碼將獲取當前的全局日誌級別並將其存儲在 `current_level` 變量中，以便進行後續的處理。
### 注意事項
- 獲取的全局日誌級別可以用於後續的判斷和處理，例如根據不同的級別來執行不同的日誌輸出設置或日誌消息處理。