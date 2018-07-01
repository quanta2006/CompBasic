title: 03. VI编辑器 ADV
speaker: LI YANG
transition: slide3
files: /js/demo.js,/css/demo.css
theme: light
usemathjax: yes


[slide]
# VIM



[slide]
# 2.6 高级编辑
- `d...`： 删除...
- `dd`： 删除一行
- `D`： 删除到行尾
- `y`： 复制
- `yy` / `Y`： 复制当前行
- `j`： 拼接行
- `p` / `P`： 粘贴 `后部` / `前部`
- `o` / `O`： 新建空行 `后部` / `前部`
- `s` / `S`： 删除 `字符` / `整行` 切换插入模式
- `C`： 删除后部，切换插入模式
- `<` / `>`： `取消缩进` / `缩进`

[slide]
<img src="img/com-vim-05.png" alt="">

[slide]
# 2.7 复杂模式
- `i` / `I`： 当前位置插入 / 行首插入
- `a` / `A`： 当前位置之后插入 / 行尾插入
- `r` / `R`： 替换当前位置字符 / 替换模式
- `v` / `V`： 可视模式 / 可视行模式

[slide]
<img src="img/com-vim-06.png" alt="">


[slide]
# 2.8 查询
- `/` / `?`： 向 `下` / `上` 查找
- `n` / `N`： 继续向 `下` / `上` 查找
- `*` / `#`： 向 `下` / `上` 查找光标处单词（要完全符合）

<img src="img/com-vim-07.png">

[slide]
# 2.9 替换 
`:[range]s/pattern/string/[c,e,g,i]`

- range： 指的是範圍，`1,7` 指從第一行至第七行，`1,$` 指從第一行至最後一行，也就是整篇文章，也可以 % 代表。
- pattern： 就是要被替換掉的字串，可以用 regexp 來表示。
- string： 將 pattern 由 string 所取代。
- c： confirm，每次替換前會詢問。
- e： 不顯示 error。
- g：  globe，不詢問，整行替換。
- i： ignore 不分大小寫。

> g 一般都要加，否則只替換每一行的第一個符合的字符串


[slide]
# 2.10 书签
- `mx`： `x` 代表 26 个小写英文字母，当前光标处就会被记录
- ``x`： 跳到书签位置位置
