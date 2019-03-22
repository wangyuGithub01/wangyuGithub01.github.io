# Linux常用指令
## 目录和文件相关

操作 | 用处
---|---
pwd | 显示当前目录
cp -r dir1 dir2 | 递归复制dir1下的所有内容到dir2
mv | 移动/更名

## 文本文件内容查看
操作 | 用处
---|---
cat file | 从第一行开始查看文件
tac file | 最后一行开始
nl | 显示文件内容同时显示行号
more | 一页一页的看
less | 比more更好的是可以向前翻页
head -n 10 | 显示前10行
tail -n 10 | 显示后10行
grep | 分析一行信息，常用在管道里，eg. cat aaa.txt \| grep "root" 或者 grep "root" aaa.txt，显示文件aaa里包含“root”的行的内容

## 查看系统信息
操作 | 用处
---|---
df  | 磁盘使用量
df -h | 以比较好读的方式显示使用量，比如1Kb而不是1024
top | 内存使用量，再按“c”可以看到command的具体信息