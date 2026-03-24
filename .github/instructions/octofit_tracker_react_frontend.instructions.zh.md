---
applyTo: "octofit-tracker/frontend/**"
---

# Octofit-tracker 健身应用 React 前端 指南（中文翻译）

## REACT 前端应用结构

请在所有命令中指向 `octofit-tracker/frontend` 目录：

```bash
npx create-react-app octofit-tracker/frontend --template cra-template --use-npm

npm install bootstrap --prefix octofit-tracker/frontend

# 在 `src/index.js` 的最顶部添加 Bootstrap CSS 导入：
sed -i "1iimport 'bootstrap/dist/css/bootstrap.min.css';" octofit-tracker/frontend/src/index.js

npm install react-router-dom --prefix octofit-tracker/frontend

```

## OctoFit Tracker 应用所用图片

应用所用的图片位于仓库根目录：`docs/octofitapp-small.png`
