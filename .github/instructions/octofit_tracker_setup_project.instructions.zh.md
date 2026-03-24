---
applyTo: "**"
---

# Octofit-tracker 健身应用 项目设置与结构 指南（中文翻译）

## 说明 Octofit Tracker 应用的目标与步骤

我要构建一个 Octofit Tracker 应用，包含以下功能：

- 用户认证与个人资料
- 活动记录与追踪
- 团队创建与管理
- 竞争性排行榜
- 个性化锻炼建议

## 运行代理模式命令时不要切换目录

- 请勿切换目录
- 在发出命令时改为显式指向相应目录

## 端口转发

- 8000: 公共
- 3000: 公共
- 27017: 私有

不要建议任何其他要转发或公开的端口

## OctoFit Tracker 应用结构

该部分定义 OctoFit Tracker 应用的目录结构：

```text
octofit-tracker/
├── backend/
│   ├── venv/
|   ├── octofit_tracker/
└── frontend/
```

## 创建 OctoFit Tracker 的 Python 虚拟环境

- 要创建虚拟环境，请运行以下命令：

  ```bash
  python3 -m venv octofit-tracker/backend/venv
  ```

## OctoFit Tracker 所需的 Python 包

### 在 `octofit-tracker/backend/requirements.txt` 中创建文件

- 将下列依赖加入 `octofit-tracker/backend/requirements.txt`
- 仅为本项目安装下列 Python 包

```text
Django==4.1.7
djangorestframework==3.14.0
django-allauth==0.51.0
django-cors-headers==4.5.0
dj-rest-auth==2.2.6
djongo==1.3.6
pymongo==3.12
sqlparse==0.2.4
stack-data==0.6.3
sympy==1.12
tenacity==9.0.0
terminado==0.18.1
threadpoolctl==3.5.0
tinycss2==1.3.0
tornado==6.4.1
traitlets==5.14.3
types-python-dateutil==2.9.0.20240906
typing_extensions==4.9.0
tzdata==2024.2
uri-template==1.3.0
urllib3==2.2.3
wcwidth==0.2.13
webcolors==24.8.0
webencodings==0.5.1
websocket-client==1.8.0
```

## Python 虚拟环境安装说明

创建 `requirements.txt` 后，安装依赖：

```bash
source octofit-tracker/backend/venv/bin/activate
pip install -r octofit-tracker/backend/requirements.txt
```

## mongodb-org 服务与数据创建

- 总是使用 `ps aux | grep mongod` 检查 `mongod` 是否在运行
- `mongodb-org` 是官方的 MongoDB 包
- `mongosh` 是官方的客户端工具
- 始终使用 Django 的 ORM，而不是直接使用 MongoDB 脚本来创建数据库结构与数据
