# file

* `file`
  * 是个命令行工具，可以在`Linux`/`Android`和`macOS`/`iOS`中查看文件的格式

## 举例

### Mac

* rsync
  ```bash
  ➜  bin pwd
  /usr/local/Cellar/rsync/3.2.7_1/bin

  ➜  bin file rsync
  rsync: Mach-O 64-bit executable x86_64
  ```
* readelf
  ```bash
  ➜  ~ file /opt/homebrew/opt/binutils/bin/readelf
  /opt/homebrew/opt/binutils/bin/readelf: Mach-O 64-bit executable arm64
  ```
* python64.dylib
  ```bash
  ➜  plugins pwd
  /Applications/IDA Pro 7.0/ida.app/Contents/MacOS/plugins
  ➜  plugins ll
  total 33776
  ...
  -rw-r--r--@  1 crifan  admin   113K  9 14  2017 python.dylib
  -rw-r--r--@  1 crifan  admin   113K  9 14  2017 python64.dylib
  ...

  ➜  plugins file python64.dylib
  python64.dylib: Mach-O 64-bit dynamically linked shared library x86_64
  ```

#### FAT格式

* FAT格式的rsync
  ```bash
  ➜  ~ which rsync
  /usr/bin/rsync
  ➜  ~ file /usr/bin/rsync
  /usr/bin/rsync: Mach-O universal binary with 2 architectures: [x86_64:Mach-O 64-bit executable x86_64] [arm64e:Mach-O 64-bit executable arm64e]
  /usr/bin/rsync (for architecture x86_64):    Mach-O 64-bit executable x86_64
  /usr/bin/rsync (for architecture arm64e):    Mach-O 64-bit executable arm64e
  ```

更多例子详见：

[FAT举例 · 可执行文件格式：Mach-O (crifan.org)](https://book.crifan.org/books/exec_file_format_macho/website/macho_format/fat/examples.html)
