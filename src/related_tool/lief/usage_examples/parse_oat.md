# 用LIEF解析OAT

代码：

```py
import lief

oat = lief.parse("SomeOAT")
for s in oat.dynamic_symbols:
  print(s)
```

输出：

```bash
oatdata                       OBJECT    GLOBAL    1000      1262000
oatexec                       OBJECT    GLOBAL    1263000   10d4060
oatlastword                   OBJECT    GLOBAL    233705c   4
oatbss                        OBJECT    GLOBAL    2338000   f5050
oatbsslastword                OBJECT    GLOBAL    242d04c   4
```
