# Compiler YxStar
A simple compiler for YxStar, generate intto TISC(Triple Instruction Set Computing)

## YxStar

以 '.yx' 结尾的文件，语法类似 C 语言，支持库函数 `getchar`, `putchar`, `printf`, `puts`， 使用前需要声明。

## TISC

这是一个三指令集的极简化设计：

- `msubleq a b c;` 
  
- `rsubleq a b c;`

- `ldorst a b c;`

该指令集的计算机的基本组成部分为 `mem[..]`, `reg[32]`, `pc`。我们的存储单元全部都是 32 位的有符号整数类型。

每条指令占据 4 个存储单元，其中 `opcode = (msubleq | rsubleq | ldorst)` 占据 1 个存储单元，`a`, `b`, `c` 3 个参数分别占据 1 个存储单元。

如果你想定义常量，可以按照以下方式：

- `. label : data`

表示在该内存区域放入 `data` 这一个整数，`label` 则表示该内存的地址，方便快速引用，当然，你可以使用指令随时更改该内存储存的内容。

## 相关阅读

OISC : One Instruction Set Computing
ZISC : Zero Instruction Set Computing
NISC : No Instruction Set Computing


