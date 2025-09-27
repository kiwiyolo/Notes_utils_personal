# Jupyter Notebook 快速参考手册

## Markdown 语法

### 常用格式
```markdown
# 标题1
## 标题2
**粗体** *斜体* `代码`

- 列表项
1. 编号列表

| 表头 | 表头 |
|------|------|
| 数据 | 数据 |

$E=mc^2$  # 行内公式
```

## 常用快捷键

### 命令模式（Esc）
- `Enter`: 进入编辑模式
- `A/B`: 上/下插入单元格
- `D,D`: 删除单元格
- `M/Y`: 转Markdown/代码
- `Shift+M`: 合并单元格
- `Ctrl+S`: 保存

### 编辑模式（Enter）
- `Shift+Enter`: 运行并下移
- `Ctrl+Enter`: 运行当前
- `Alt+Enter`: 运行并插入
- `Tab`: 代码补全
- `Shift+Tab`: 查看文档

## Magic Commands

### 行魔法
```python
%timeit x*x  # 计时
%run script.py  # 运行脚本
%pwd  # 当前目录
%ls  # 系统命令
%matplotlib inline  # 内嵌图形
```

### 单元格魔法
```python
%%time  # 整个单元格计时
%%writefile file.py  # 写入文件
```

## 调试技巧

### pdb 基本使用
```python
import pdb; pdb.set_trace()  # 设置断点

# 调试命令：
# n(ext) - 下一行
# s(tep) - 进入函数
# c(ontinue) - 继续
# p(rint) - 打印变量
# q(uit) - 退出
```

## 实验记录模板

```markdown
# 实验 - [名称]
**日期**: YYYY-MM-DD  
**目标**: [简要描述]

## 参数设置
```python
params = {'lr': 0.01, 'epochs': 100}
```

## 结果
| 指标 | 训练集 | 测试集 |
|------|--------|--------|
| 准确率 | 0.95 | 0.89 |

## 结论
- 主要发现: [要点]
- 下一步: [计划]
```

## 扩展功能

### 安装
```bash
pip install jupyter_contrib_nbextensions
jupyter contrib nbextension install --user
```

### 推荐扩展
- **Table of Contents**: 自动目录
- **ExecuteTime**: 执行时间显示
- **Variable Inspector**: 变量查看器
- **Codefolding**: 代码折叠

## 导出格式

```bash
# 常用导出命令
jupyter nbconvert notebook.ipynb --to html
jupyter nbconvert notebook.ipynb --to pdf
jupyter nbconvert notebook.ipynb --to markdown
jupyter nbconvert notebook.ipynb --to python

# 仅导出结果（无代码）
jupyter nbconvert notebook.ipynb --to html --TemplateExporter.exclude_input=True
```

## 实用小贴士

1. **使用 `# %%` 分隔代码块**，便于分段运行
2. **定期 `Ctrl+S` 保存**，防止数据丢失
3. **用 `tmux` 保持长时间运行**：
   ```bash
   tmux new -s jupyter
   jupyter notebook
   # Ctrl+B then D 分离会话
   ```
4. **变量查看**: 在最后一行直接写变量名显示值
5. **魔法命令调优**：
   ```python
   %config InlineBackend.figure_format = 'retina'  # 高清图形
   %load_ext autoreload
   %autoreload 2  # 自动重载模块
   ```

6. **大数据处理**：使用分块读取
   ```python
   for chunk in pd.read_csv('large.csv', chunksize=10000):
       process(chunk)
   ```

7. **性能分析**：
   ```python
   %prun expensive_function()  # 性能分析
   %debug  # 事后调试
   ```

---

*简洁高效，科研必备！*
