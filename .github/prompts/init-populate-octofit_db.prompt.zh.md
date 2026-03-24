---
mode: "agent"
model: GPT-4.1
description: "为 Octofit Tracker Django 应用配置并填充 octofit_db 测试数据"
---

# 环境设置

- 使用存在的 Python 虚拟环境：`octofit-tracker/backend/venv`。
- 不要创建新的虚拟环境。
- 激活方式：`source octofit-tracker/backend/venv/bin/activate`
- 已安装 `mongodb-org-shell`；使用 `mongosh` 与 MongoDB 交互。
- Django 项目位于 `octofit-tracker/backend/octofit_tracker`。

# 数据库初始化与填充

1. 确保 MongoDB 服务正在运行。
2. 在 `settings.py` 中配置 Django，使其使用 Djongo 连接到名为 `octofit_db` 的数据库，且不需要认证或密码。
3. 确认 `octofit_tracker`、`rest_framework` 和 `djongo` 在 `INSTALLED_APPS` 中。
4. 在 `settings.py` 中启用 CORS，允许所有来源、方法和头。允许所有主机 `*`。
5. 安装并配置 CORS 中间件组件。
6. 在虚拟环境中运行 `makemigrations` 和 `migrate`。
7. 初始化 `octofit_db` 数据库并为 `users`、`teams`、`activities`、`leaderboard` 和 `workouts` 创建集合。
8. 确保在用户集合的 `email` 字段上建立唯一索引（例如：`db.users.createIndex({ "email": 1 }, { unique: true })`）。
9. 使用位于 `octofit-tracker/backend/octofit_tracker/management/commands/populate_db.py` 的 Django 管理命令填充测试数据：
   a. 帮助信息：'Populate the octofit_db database with test data'.
   b. 使用 Django ORM 进行数据删除与插入。
   c. 示例数据使用超级英雄，并使用团队 `marvel` 与 `dc`。
10. 使用 `mongosh` 验证数据库与集合已创建并填充成功。
11. 列出 `octofit_db` 数据库中的集合并展示每个集合的示例文档。

# 验证

- 填充完成后，使用 `mongosh` 验证 `octofit_db` 包含正确的集合与测试数据。
- 确认针对所有集合的 Django REST API 端点可用。
