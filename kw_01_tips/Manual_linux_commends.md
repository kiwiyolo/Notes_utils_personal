# Linux 常用命令简明手册

## 1. `cat` - 文件内容查看器
**用途**：显示文件内容或创建新文件  
**常用操作**：
- 查看文件：`cat filename`
- 创建文件：`cat > newfile`（输入内容后按 Ctrl+D 保存）
- 合并文件：`cat file1 file2 > combined_file`

## 2. `echo` - 文本输出器
**用途**：显示文本消息  
**常用操作**：
- 显示文本：`echo "Hello World"`
- 写入文件：`echo "text" > file`
- 追加内容：`echo "more text" >> file`

## 3. `seq` - 数字序列生成器
**用途**：生成数字序列  
**常用操作**：
- 生成1-5：`seq 5`
- 指定范围：`seq 3 7`
- 带步长：`seq 1 2 10`（输出1,3,5,7,9）

## 4. `sort` - 文本排序器
**用途**：对文本行排序  
**常用操作**：
- 排序文件：`sort file`
- 数字排序：`sort -n file`
- 反向排序：`sort -r file`

## 5. `cut` - 列提取器
**用途**：提取文件中的指定列  
**常用操作**：
- 提取第1列：`cut -f1 file`（默认Tab分隔）
- 逗号分隔：`cut -d',' -f1,3 file`
- 提取字符：`cut -c1-5 file`

## 6. `tr` - 字符转换器
**用途**：替换或删除字符  
**常用操作**：
- 小写转大写：`tr 'a-z' 'A-Z' < file`
- 删除字符：`tr -d ',' < file`
- 压缩重复：`tr -s ' ' < file`（多个空格变单个）

## 7. `diff` - 文件比较器
**用途**：比较文件差异  
**常用操作**：
- 比较文件：`diff file1 file2`
- 并排显示：`diff -y file1 file2`
- 忽略空格：`diff -w file1 file2`

## 8. `uniq` - 重复行处理器
**用途**：去除重复行  
**常用操作**：
- 去重：`uniq file`（需先排序）
- 计数：`uniq -c file`
- 仅显重复：`uniq -d file`

## 组合使用示例
```bash
# 统计单词频率
cat file.txt | tr ' ' '\n' | sort | uniq -c | sort -nr

# 提取CSV特定列
cut -d',' -f2,4 data.csv | sort | uniq

# 生成测试序列
seq 100 | sort -R | head -5  # 随机5个数字
```

## 快速参考表
| 命令 | 主要功能 | 常用参数 |
|------|----------|----------|
| `cat` | 显示/创建文件 | `>` 创建, `>>` 追加 |
| `echo` | 输出文本 | `-n` 不换行 |
| `seq` | 生成序列 | `-s` 指定分隔符 |
| `sort` | 排序文本 | `-n` 数字, `-r` 反向 |
| `cut` | 提取列 | `-d` 分隔符, `-f` 字段 |
| `tr` | 字符替换 | `-d` 删除, `-s` 压缩 |
| `diff` | 比较文件 | `-y` 并排, `-w` 忽略空格 |
| `uniq` | 处理重复 | `-c` 计数, `-d` 显重复 |

> 提示：使用 `命令 --help` 查看详细帮助（如 `cat --help`）
