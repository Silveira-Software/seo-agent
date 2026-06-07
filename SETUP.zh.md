# 设置指南

## 步骤1 — 安装依赖
```bash
pip install -r requirements.txt
```

## 步骤2 — Google Search Console OAuth（10分钟）

1. 前往 https://console.cloud.google.com/
2. 创建新项目（或选择现有项目）
3. 进入 **API和服务 → 库**
4. 搜索"Google Search Console API" → 启用
5. 进入 **API和服务 → 凭据**
6. 点击 **创建凭据 → OAuth客户端ID**
7. 应用类型：**桌面应用**
8. 下载JSON文件 → 重命名为`credentials.json`
9. 将`credentials.json`放在项目文件夹根目录

## 步骤3 — 设置.env文件
```bash
cp .env.example .env
```
编辑`.env`并设置：
- `GSC_SITE_URL` — 你的Search Console属性URL
  - 域属性：`sc-domain:yourdomain.com`
  - URL前缀属性：`https://www.yourdomain.com/`

## 步骤4 — 首次运行（触发浏览器OAuth登录）
```bash
python scripts/gap_finder.py
```
浏览器窗口将打开，要求你用Google账号授权。
授权后会保存`token.pickle`文件——之后无需重新授权。

## 步骤5 — 让Claude Code运行工作流
在此项目文件夹中打开Claude Code，输入：
```
运行本周的缺口分析
```

## 步骤6 — 运行完整的每周工作流
```
运行完整的每周工作流
```

## 可选 — DataForSEO设置
在 https://dataforseo.com 注册（按用量付费，典型使用约$50/月）。
将登录名和密码添加到`.env`。
这将解锁真实搜索量数据和竞争对手反向链接分析。
