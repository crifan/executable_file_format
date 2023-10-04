# LIEF解析Mach-O

从`Mach-O`中解析`__text`、`__data`等section的内容：

```py
import lief

# --- Extract __text and __data section content from the binary ---
binary = lief.parse("uncrackable.arm64")
text_section = binary.get_section("__text")
text_content = text_section.content

data_section = binary.get_section("__data")
data_content = data_section.content
```
