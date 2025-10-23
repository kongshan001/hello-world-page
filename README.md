# Hello World - GitHub Pages 部署指南

这是一个简单的 Hello World 网站，使用 GitHub Pages 和 GitHub Actions 自动部署。

## 项目内容

- `index.html` - 主页面，包含精美的 Hello World 展示
- `.github/workflows/deploy.yml` - GitHub Actions 自动部署工作流
- `.gitignore` - Git 忽略文件配置
- `README.md` - 本说明文档

## 部署步骤

### 第一步：在 GitHub 上创建仓库

1. 登录您的 GitHub 账号
2. 点击右上角的 "+" 号，选择 "New repository"
3. 填写仓库信息：
   - **Repository name**: 填写您想要的仓库名称（例如：`hello-world-page`）
   - **Description**: （可选）"My first GitHub Pages website"
   - **Public/Private**: 选择 **Public**（公开仓库才能使用免费的 GitHub Pages）
   - **不要**勾选 "Initialize this repository with a README"（因为我们已经有本地文件）
4. 点击 "Create repository"

### 第二步：推送代码到 GitHub

在您的终端中，确保当前目录在项目根目录下，然后执行以下命令：

```bash
# 添加所有文件到 Git
git add .

# 提交更改
git commit -m "Initial commit: Add Hello World page"

# 将 main 设置为默认分支（如果需要）
git branch -M main

# 添加 GitHub 远程仓库（请替换为您自己的仓库地址）
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git

# 推送代码到 GitHub
git push -u origin main
```

**注意**: 请将 `YOUR_USERNAME` 替换为您的 GitHub 用户名，将 `YOUR_REPOSITORY_NAME` 替换为您在第一步创建的仓库名称。

### 第三步：配置 GitHub Pages

1. 进入您的 GitHub 仓库页面
2. 点击 "Settings"（设置）标签
3. 在左侧菜单中找到 "Pages"
4. 在 "Build and deployment" 部分：
   - **Source**: 选择 "GitHub Actions"
5. 保存设置

### 第四步：等待部署完成

1. 推送代码后，GitHub Actions 会自动触发部署
2. 在仓库页面点击 "Actions" 标签查看部署进度
3. 等待工作流完成（通常需要 1-3 分钟）
4. 部署成功后，会显示绿色的对勾标记

### 第五步：访问您的网站

部署成功后，您的网站将在以下地址可访问：

```
https://YOUR_USERNAME.github.io/YOUR_REPOSITORY_NAME/
```

例如，如果您的用户名是 `johndoe`，仓库名是 `hello-world-page`，则网站地址为：

```
https://johndoe.github.io/hello-world-page/
```

## 后续更新

当您需要更新网站内容时：

1. 修改 `index.html` 或其他文件
2. 提交并推送更改：

```bash
git add .
git commit -m "Update website content"
git push
```

3. GitHub Actions 会自动重新部署您的网站
4. 等待 1-3 分钟后，访问网站查看更新

## 故障排除

### 404 错误

如果访问网站时出现 404 错误：

1. 确保在 Settings > Pages 中选择了 "GitHub Actions" 作为 Source
2. 检查 Actions 标签，确认部署工作流已成功运行
3. 等待几分钟让 DNS 传播生效
4. 清除浏览器缓存后重试

### 部署失败

如果 GitHub Actions 部署失败：

1. 进入 Actions 标签查看错误日志
2. 确认仓库是公开的（Public）
3. 检查 Settings > Actions > General，确保启用了 "Read and write permissions"

### 权限问题

如果遇到权限错误：

1. 进入 Settings > Actions > General
2. 在 "Workflow permissions" 部分：
   - 选择 "Read and write permissions"
   - 勾选 "Allow GitHub Actions to create and approve pull requests"
3. 点击 "Save" 保存设置
4. 重新运行工作流

## 自定义域名（可选）

如果您想使用自定义域名：

1. 在项目根目录创建 `CNAME` 文件，内容为您的域名（例如：`www.example.com`）
2. 在您的域名提供商处配置 DNS 记录：
   - 添加 CNAME 记录指向 `YOUR_USERNAME.github.io`
   - 或添加 A 记录指向 GitHub Pages IP 地址
3. 在 GitHub 仓库 Settings > Pages 中输入您的自定义域名
4. 等待 DNS 传播（可能需要几小时到 48 小时）

## 技术特点

- **纯静态 HTML**: 无需构建步骤，直接部署
- **自动化部署**: 使用 GitHub Actions，推送即部署
- **响应式设计**: 自适应桌面和移动设备
- **现代化样式**: 使用渐变背景、玻璃态效果和动画
- **零成本**: 完全免费托管

## 资源链接

- [GitHub Pages 官方文档](https://docs.github.com/en/pages)
- [GitHub Actions 文档](https://docs.github.com/en/actions)
- [自定义域名配置](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

## 许可证

MIT License - 您可以自由使用、修改和分发此项目。

---

**祝您部署成功！如有问题，请查看 GitHub 仓库的 Issues 页面。**
