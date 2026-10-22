# 文件关键词扫描报告器

一个用 Python 写的初学者友好小工具：手动指定一个文件夹和一组关键词，只读扫描 `.txt`、`.md`、`.csv` 文件，统计关键词出现次数和所在行号，并生成一份 Markdown 报告。

## 特性

- **只读扫描**：只读取文件内容，不修改任何原文件
- **多格式支持**：支持 `.txt`、`.md`、`.csv` 三种常见文档格式
- **智能过滤**：自动跳过超大文件和二进制文件
- **详细报告**：生成 Markdown 格式的扫描报告，包含关键词出现次数和行号
- **无需依赖**：仅使用 Python 标准库，无需安装第三方包

## 项目结构

```
file_keyword_scanner_v0.1/
├── main.py            # 命令行入口：参数解析、输入校验、流程调度
├── scanner.py         # 核心：遍历文件夹、过滤、读取、搜索、统计
├── report.py          # 生成 Markdown 报告
├── logger.py          # 日志写入
├── config.py          # 默认配置（扩展名、输出目录、大小限制等）
├── sample_data/       # 示例数据
│   ├── notes.txt
│   ├── readme_example.md
│   └── data.csv
├── requirements.txt   # 仅标准库，无需第三方依赖
└── .gitignore         # 忽略 output/、__pycache__/、*.log
```

## 依赖

仅使用 Python 标准库，无需额外安装。

## 使用方法

### 基本用法

```bash
python main.py <文件夹路径> <关键词1> [关键词2] [关键词3] ...
```

### 参数说明

- `<文件夹路径>`：要扫描的文件夹路径
- `<关键词>`：要搜索的关键词，支持多个关键词

### 示例

```bash
# 扫描当前目录下的 sample_data 文件夹，搜索 "Python" 和 "扫描" 两个关键词
python main.py sample_data Python 扫描

# 扫描指定目录
python main.py /path/to/your/folder 关键词1 关键词2
```

### 输出

运行完成后，会在 `output` 目录下生成：

- `scan_report.md` - 扫描结果报告
- `scanner.log` - 运行日志

## 配置说明

可在 `config.py` 中修改以下默认配置：

| 配置项 | 说明 | 默认值 |
|--------|------|--------|
| DEFAULT_EXTENSIONS | 支持的文件扩展名 | txt, md, csv |
| DEFAULT_OUTPUT_DIR | 输出目录 | output |
| MAX_FILE_SIZE | 单个文件最大读取大小 | 10 MB |
| FILE_ENCODING | 文件编码 | utf-8 |
| BINARY_CHECK_BYTES | 二进制文件探测字节数 | 512 |

## 后续计划

- 添加系统桌面窗口 UI
- 支持更多文档格式

## 许可证

MIT License