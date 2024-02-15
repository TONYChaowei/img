**# Linux中正则的运用** 



**## 实验条件**

\- /bin/bin/zsh中 或 /bin/bash使用 

\- 所有数据都是现生成的



**### 使用seq生成数据 开头和结尾**

\```bash

seq 20 2 100 | head -5



Desc:

这条命令用于生成从 20 到 100 之间的等差数列，步长为 2，并且只输出前 5 个数。

\- `seq 20 2 100`: 这个部分生成了一个从 20 开始，以 2 为步长，到 100 结束的等差数列。

\- `|`: 管道符号，将前一个命令的输出传递给下一个命令。

\- `head -5`: 这个部分表示只取输出结果的前 5 行。

\```

![](https://cdn.jsdelivr.net/gh/TONYChaowei/img@master/Reg/1.png)





\```bash

seq 20 2 100 | grep '5'

过滤包含数字5的数据，还可以重定向到指定文件 

例：

seq 20 2 100 | grep '5' > test.txt

\```

![](https://cdn.jsdelivr.net/gh/TONYChaowei/img@master/Reg/2.png)



现在来匹配正则过滤

\```bash

seq 20 2 100 | grep '^5'

显示数字开头为5的数字

seq 20 2 100 | grep '2$'

显示数字尾数为5的数字

seq 20 2 100 | grep -E '^5|2$'

这里是使用-E 是使用 拓展的版本

\```

![](https://cdn.jsdelivr.net/gh/TONYChaowei/img@55501f2a4182f04be44946d09b3ae05064ceca91/Reg/3.png)