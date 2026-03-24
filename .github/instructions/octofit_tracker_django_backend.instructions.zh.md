---
applyTo: "octofit-tracker/backend/**"
---

# Octofit-tracker 健身应用 Django 后端 指南（中文翻译）

## Django 后端应用结构

### settings.py

应始终包含以下内容：

```python
import os
ALLOWED_HOSTS = ['localhost', '127.0.0.1']
if os.environ.get('CODESPACE_NAME'):
    ALLOWED_HOSTS.append(f"{os.environ.get('CODESPACE_NAME')}-8000.app.github.dev")
```

## serializers.py

```text
序列化器应将 ObjectId 字段转换为字符串
```

## REST API 端点

```text
使用 `curl` 来测试端点
```

### urls.py

应始终使用 Codespace 环境变量来构建 URL：

```python
import os
codespace_name = os.environ.get('CODESPACE_NAME')
if codespace_name:
    base_url = f"https://{codespace_name}-8000.app.github.dev"
else:
    base_url = "http://localhost:8000"

urlpatterns = [
    path('admin/', admin.site.urls),
    path('api/', api_root, name='api-root'),
    path('api/', include(router.urls)),
]
```
