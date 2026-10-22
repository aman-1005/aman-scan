文件关键词扫描报告器

一个用 Python 写的初学者友好小工具：手动指定一个文件夹和一组关键词，只读扫描 `.txt`、`.md`、`.csv` 文件，统计关键词出现次数和所在行号，并生成一份 Markdown 报告。

第一版是《无 UI 的核心引擎》，重点不是界面，而是把自动化流程跑通：手动触发 → 条件过滤 → 只读扫描 → 统计 → 生成报告 → 写日志。

项目坚持只读、预览优先、不覆盖原文件。后续计划再套一个系统桌面窗口 UI，并逐步支
持更多文档格式

我暂时用ai写个文件树给你们看一下
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
├── .gitignore         # 忽略 output/、__pycache__/、*.log
└── README.md