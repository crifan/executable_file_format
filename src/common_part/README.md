# 通用内容

## 核心点和通用点

不同可执行文件格式的内部，最核心的是：

* 编译和链接的过程
  * 涉及到编译器和链接器
    * 如何生成代码？
    * 把生成的代码和数据，放到什么地方？
    * 运行时如何加载这些代码和数据？
      * 才能确保程序能正常执行

## 不用文件格式的通用内容

* 各种的
  * Segment段
    * 代码段
      * `.text`
    * 数据段
      * `.data`
    * 等等
  * section区
    * `.bss`
    * `.data`
    * `.rodata`
    * 等等

## 函数调用逻辑

When a program wants to call a function, it actually does following flow:

* 1.It made a jump to relevant entry in PLT (Procedure Linkage Table)
* 2.In PLT, there is another jump to an address mentioned in related entry in GOT (Global Offset Table)
* 3.If this is the first the function is called, follow step #4. If this isn't, follow step #5.
* 4.The related GOT entry contains an address that points back to next instruction in PLT. Program will jump to this address and then calls the dynamic linker to resolve the function's address. If the function is found, its address is put in related GOT entry and then the function itself is executed.
  * So, another time the function is called, GOT already holds its address and PLT can jump directly to the address. This procedure is called lazy binding; all external symbols are not resolved until the time it is really needed (in this case, when a function is called). Jump to step #6
* 5.Jump to the address mentioned in GOT. It is the address of the function thus PLT is no longer used
* 6.Execution of the function is finished. Jump back to the next instruction in the main program.

-》

* 1.跳转到PLT=Procedure Linkage Table中的对应入口
* 2.PLT中还有另外一个跳转，跳转到GOT=Global Offset Table中相关的入口
* 3.如果函数找到了被调用了，则继续步骤4，否则继续步骤5
* 4. GOT入口中包括了一个地址，指向了PLT中的下一个指令
  * 程序会调到转该指令，谈话调用动态链接器去继续函数地址。
    * 如果函数找到了，则该函数地址被放到GOT入口中，然后函数自己被执行
  * 如果下一次函数被执行时，GOT中已有其地址，所以PLT可以直接跳转到对应地址
    * 此过程叫做懒绑定lazy binding
      * 所有外部符号都不会去解析，直到去真正要执行之前，需要解析，才去解析
* 5.跳转到GOT中提到的函数的地址。所以就不用PLT了。
* 执行函数，直到结束。跳转会主程序中的下一个指令。

