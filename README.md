# Devbox Images Sync

将 Sealos 官方 devbox 镜像同步到你自己的 GitHub Container Registry。

## 使用方法

### 1. 创建 GitHub 仓库

在 GitHub 上创建一个新仓库，比如 `devbox-images`

### 2. 上传文件

将 `.github` 文件夹上传到你的仓库：

```bash
cd scripts/github-sync
git init
git add .
git commit -m "Add sync workflow"
git remote add origin git@github.com:你的用户名/devbox-images.git
git push -u origin main
```

### 3. 启用 GitHub Actions

1. 进入仓库 Settings → Actions → General
2. 确保 "Allow all actions" 已启用
3. 在 "Workflow permissions" 中选择 "Read and write permissions"

### 4. 手动触发同步

1. 进入 Actions 标签页
2. 选择 "Sync Devbox Images" workflow
3. 点击 "Run workflow"

### 5. 使用你的镜像

同步完成后，镜像地址变为：
```
ghcr.io/你的用户名/devbox-runtime/go-1.22.5:latest
ghcr.io/你的用户名/devbox-runtime/python-3.12:latest
...
```

## 自动同步

Workflow 配置为每周一自动同步一次。你也可以修改 `cron` 表达式调整频率。

## 镜像列表

- **语言**: go, node.js, python, php, .net
- **框架**: next.js, nuxt, vue, django, flask, express 等
- **系统**: ubuntu, debian, nginx
