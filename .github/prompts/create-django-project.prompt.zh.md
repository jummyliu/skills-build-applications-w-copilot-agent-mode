---
mode: "agent"
model: GPT-4.1
description: "在 octofit-tracker/backend/octofit_tracker 目录中创建并启动 Django 项目"
---

你的任务是在 `octofit-tracker/backend/octofit_tracker` 目录中使用已创建的 Python 虚拟环境（位于 `octofit-tracker/backend/venv`，已包含所有先决条件）来创建 Django 项目。

创建 Django 项目请按照以下步骤：

1. 确保我们在仓库根目录，且不要切换目录
2. `source octofit-tracker/backend/venv/bin/activate`
3. 在 `octofit-tracker/backend` 目录中运行 `django-admin startproject octofit_tracker`
4. `python manage.py migrate`
5. 指示用户使用仓库中 `.vscode/launch.json` 中的配置来运行 Django 应用
