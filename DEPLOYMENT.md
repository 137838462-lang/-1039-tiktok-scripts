# 1039市场采购 × TikTok爆款文案库 - 部署指南

本文档提供了将网站部署到Vercel并获得永久域名的完整步骤。

## 📋 前置要求

- GitHub账户（免费）
- Vercel账户（免费，可用GitHub账户登录）
- 本项目的源代码文件

## 🚀 快速部署步骤

### 第一步：创建GitHub仓库

1. 登录 [GitHub](https://github.com)
2. 点击右上角 **+** 图标，选择 **New repository**
3. 填写仓库信息：
   - **Repository name**: `1039-tiktok-scripts`
   - **Description**: `1039市场采购 × TikTok爆款口播文案库`
   - **Visibility**: 选择 **Public**（这样Vercel可以访问）
4. 点击 **Create repository**

### 第二步：推送代码到GitHub

在您的本地计算机或服务器上执行以下命令：

```bash
# 进入项目目录
cd /home/ubuntu/tiktok_scripts_web

# 添加远程仓库（将YOUR_USERNAME替换为您的GitHub用户名）
git remote add origin https://github.com/YOUR_USERNAME/1039-tiktok-scripts.git

# 重命名分支为main（可选，但推荐）
git branch -M main

# 推送代码到GitHub
git push -u origin main
```

**如果遇到身份验证问题**，请使用个人访问令牌(PAT)：
```bash
# 使用PAT进行身份验证
git push -u origin main
# 当提示输入用户名时，输入您的GitHub用户名
# 当提示输入密码时，输入您的个人访问令牌
```

[如何创建GitHub个人访问令牌？](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

### 第三步：在Vercel上部署

#### 方法A：使用Vercel Web界面（推荐新手）

1. 访问 [Vercel官网](https://vercel.com)
2. 点击 **Sign Up** 或 **Log In**
3. 选择 **Continue with GitHub** 进行OAuth授权
4. 授权Vercel访问您的GitHub账户
5. 返回Vercel后，点击 **New Project**
6. 在 **Import Git Repository** 中搜索 `1039-tiktok-scripts`
7. 选择该仓库，点击 **Import**
8. 保持默认配置，点击 **Deploy**
9. 等待部署完成（通常需要1-2分钟）

#### 方法B：使用Vercel CLI（推荐开发者）

```bash
# 全局安装Vercel CLI
npm install -g vercel

# 或使用yarn
yarn global add vercel

# 在项目目录下执行
cd /home/ubuntu/tiktok_scripts_web
vercel

# 按照提示进行身份验证和配置
# 首次部署会要求您选择团队和项目名称
```

### 第四步：配置自定义域名（可选）

如果您想使用自己的域名而不是Vercel提供的默认域名：

1. 在Vercel项目设置中找到 **Domains** 部分
2. 点击 **Add Domain**
3. 输入您的域名（例如：`1039-tiktok.com`）
4. 按照提示配置DNS记录
5. 等待DNS生效（通常需要24小时）

## 📊 部署后的自动化

一旦部署完成，以下工作流将自动进行：

- **自动构建**：每次您推送代码到GitHub时，Vercel会自动构建和部署
- **预览部署**：每个Pull Request都会生成预览链接
- **生产部署**：合并到main分支时自动部署到生产环境

## 🔄 更新网站内容

部署后，如果您想更新文案或修改网站：

1. 编辑本地的 `index.html` 或其他文件
2. 提交更改：
   ```bash
   git add .
   git commit -m "Update: 描述您的更改"
   git push
   ```
3. Vercel会自动检测到更改并重新部署
4. 大约1-2分钟后，您的网站将更新

## 🎯 获得的永久URL

部署完成后，您将获得：

- **Vercel默认域名**：`https://1039-tiktok-scripts.vercel.app`
- **自定义域名**（如已配置）：`https://your-custom-domain.com`

这个URL将**永久有效**，无需任何维护成本。

## 🆘 常见问题

### Q: 部署失败怎么办？
A: 检查以下几点：
- 确保GitHub仓库是公开的
- 确保所有文件都已正确推送
- 检查Vercel的构建日志（Build Logs）查看具体错误

### Q: 如何回滚到之前的版本？
A: 
1. 在Vercel项目的 **Deployments** 标签中找到之前的部署
2. 点击该部署的 **...** 菜单
3. 选择 **Promote to Production**

### Q: 网站加载很慢怎么办？
A: 
- Vercel会自动使用CDN加速，通常速度很快
- 如果仍然很慢，可以在Vercel设置中选择离您最近的地区

### Q: 可以离线使用这个网站吗？
A: 可以！这是一个完全静态的网站，您可以：
1. 下载所有文件到本地
2. 在浏览器中直接打开 `index.html`
3. 所有功能都可以正常使用（无需互联网连接）

## 📞 获得帮助

- **Vercel文档**：https://vercel.com/docs
- **GitHub文档**：https://docs.github.com
- **本项目问题**：在GitHub仓库中提交Issue

## ✅ 部署检查清单

- [ ] 创建了GitHub仓库
- [ ] 推送了代码到GitHub
- [ ] 在Vercel中导入了仓库
- [ ] 部署成功完成
- [ ] 测试了网站的所有功能
- [ ] （可选）配置了自定义域名
- [ ] （可选）启用了自动部署

---

**部署完成后，您的网站将永久在线，无需任何维护！** 🎉

享受您的永久网站吧！
