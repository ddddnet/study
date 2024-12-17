# Mkdocs常用命令

## Mkdocs常用命令

- `mkdocs new [dir-name]` - Create a new project.
- `mkdocs serve` - Start the live-reloading docs server.
- `mkdocs build` - Build the documentation site.
- `mkdocs gh-deploy` - 将网站部署到github pages.

## Github Actions 自动部署

```
name: site

on: # 触发条件
  push:
    branches:
      - main # 根据实际的分支情况设置

permissions: # 权限
  contents: write

jobs: # 流程
  deploy:
    runs-on: ubuntu-latest # 运行环境
    steps:
      - uses: actions/checkout@v3 # 检出代码
      - uses: actions/setup-python@v4 # 安装 Python
        with:
          python-version: 3.x
      - run: pip install mkdocs-material 
      - run: mkdocs gh-deploy --force

```