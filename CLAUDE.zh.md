# SEO代理 — mikefutia.com

## 项目简介
一个SEO智能系统，连接Google Search Console，识别关键词缺口，映射竞争对手，并生成每周内容计划和HTML仪表板——一切只需一个提示。

## 会话启动协议
每次会话开始时：
1. 阅读与今天任务相关的技能文件
2. 在任何内容任务前阅读brand-voice.md
3. 在运行下游技能前检查/reports/中的最新输出

## 可用技能
- skills/gap-finder.md — 关键词发现、缺口区分析、行动建议
- skills/competitor-intel.md — 竞争情报、威胁级别、他们为何获胜
- skills/brand-writer.md — 内容规划、文章写作、品牌语音

## 关键命令
- "运行本周的缺口分析" → 读取skills/gap-finder.md，运行scripts/gap_finder.py
- "运行竞争情报" → 读取skills/competitor-intel.md，运行scripts/competitor_intel.py
- "生成本周的内容计划" → 读取skills/brand-writer.md，运行scripts/content_plan.py
- "构建仪表板" → 运行scripts/build_dashboard.py使用本周报告
- "运行完整的每周工作流" → 按顺序运行所有四个，最后构建仪表板

## 文件结构
skills/             — 技能指令文件（Claude在执行前阅读）
scripts/            — Claude执行以产生输出的Python脚本
reports/            — 每周输出保存为.md和.json文件
drafts/             — 待审查的文章草稿
brand-voice.md      — 品牌语音档案（每周更新）
.env                — API凭据（永远不要提交）

## 输出格式规则
每个脚本保存两个文件：
1. 人类可读的.md报告 → /reports/
2. 机器可读的.json数据文件 → /reports/
仪表板构建器读取.json文件来渲染HTML输出。
