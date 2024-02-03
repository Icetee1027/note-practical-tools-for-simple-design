
----
  `std::ifstream` 属于 C++ 标准库中的 `<fstream>` 头文件，用于从文件中读取数据。

- **函数原型：**
  ```cpp
  explicit ifstream(const char* filename, ios_base::openmode mode = ios_base::in);
  explicit ifstream(const string& filename, ios_base::openmode mode = ios_base::in);
  ```

- **参数：**
  - `filename`：要打开的文件的名称。
  - `mode`：文件打开模式，默认为 `ios_base::in`，表示以读取模式打开文件。其他常用模式包括 `ios_base::out`（写入模式）、`ios_base::app`（追加模式）等。

- **返回值：**
  - 无

- **示例用法：**
  ```cpp
  #include <iostream>
  #include <fstream>

  int main() {
      std::ifstream file("example.txt"); // 打开名为 "example.txt" 的文件
      if (file.is_open()) {
          std::string line;
          while (std::getline(file, line)) { // 逐行读取文件内容
              std::cout << line << '\n'; // 输出每一行内容
          }
          file.close(); // 关闭文件
      } else {
          std::cerr << "Failed to open file!\n";
      }
      return 0;
  }
  ```

- **注意事项：**
  - 如果文件打开失败，应该检查文件路径是否正确或文件是否存在，并适当处理打开失败的情况。
  - 在使用完文件流后，应该及时调用 `close()` 方法关闭文件，释放资源。