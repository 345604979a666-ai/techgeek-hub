# TechGeek Hub - Cloudflare Pages 部署指南

## 项目结构

```
techgeek-hub/
├── index.html          # 主页面
├── css/
│   └── style.css       # 样式表
├── js/
│   ├── data.js         # 数据文件
│   └── app.js          # 应用逻辑
├── _headers            # HTTP 响应头配置
├── _redirects          # URL 重定向规则
├── wrangler.toml       # Cloudflare 配置
└── .gitignore          # Git 忽略规则
```

## 部署步骤

### 第一步：准备代码

1. 确保所有文件已保存
2. 检查 `index.html` 中的资源路径是否正确（相对路径）
3. 在浏览器中本地打开 `index.html` 测试功能是否正常

### 第二步：创建 GitHub 仓库

1. 访问 https://github.com 注册/登录
2. 点击右上角 `+` → `New repository`
3. 填写信息：
   - Repository name: `techgeek-hub`
   - Description: `技术极客社区 - 无线电、电脑、音响、网络知识分享平台`
   - 选择 `Public`（公开仓库免费）
   - 勾选 `Add a README file`（可选）
4. 点击 `Create repository`

### 第三步：上传代码到 GitHub

#### 方法一：命令行（推荐）

```bash
# 进入项目目录
cd techgeek-hub

# 初始化 Git 仓库
git init

# 添加所有文件
git add .

# 提交代码
git commit -m "Initial commit: TechGeek Hub v1.0"

# 关联远程仓库（将下面的 URL 替换为你的仓库地址）
git remote add origin https://github.com/你的用户名/techgeek-hub.git

# 推送代码
git branch -M main
git push -u origin main
```

#### 方法二：GitHub 网页上传

1. 进入你的 GitHub 仓库页面
2. 点击 `Add file` → `Upload files`
3. 拖拽或选择所有项目文件
4. 填写提交信息：`Initial commit`
5. 点击 `Commit changes`

### 第四步：连接 Cloudflare Pages

1. 访问 https://dash.cloudflare.com 登录/注册
2. 左侧菜单点击 `Pages`
3. 点击 `Create a project`
4. 选择 `Connect to Git`
5. 授权 Cloudflare 访问你的 GitHub 账号
6. 在仓库列表中找到 `techgeek-hub`，点击 `Select`
7. 开始设置：

### 第五步：配置构建设置

| 设置项 | 值 |
|--------|-----|
| Project name | `techgeek-hub`（或自定义） |
| Production branch | `main` |
| Framework preset | `None` |
| Build command | （留空，不填） |
| Build output directory | `/`（根目录） |

点击 `Save and Deploy`

### 第六步：等待部署完成

- 首次部署约需 1-3 分钟
- 部署成功后，Cloudflare 会提供默认域名：`xxx.pages.dev`
- 点击链接即可访问你的网站！

### 第七步：自定义域名（可选）

1. 在 Cloudflare Pages 项目页面，点击 `Custom domains`
2. 点击 `Set up a custom domain`
3. 输入你的域名（如 `techgeek.com`）
4. 按照提示添加 DNS 记录
5. 等待 SSL 证书自动颁发（约几分钟）

## 自动部署

Cloudflare Pages 会自动监听 GitHub 仓库的 `main` 分支：

- 每次 `git push` 到 main 分支 → 自动重新部署
- Pull Request → 自动生成预览链接
- 回滚 → 在 Cloudflare 控制台选择历史版本

## 更新网站

```bash
# 修改代码后
git add .
git commit -m "更新内容描述"
git push origin main
# Cloudflare 会自动重新部署
```

## 常见问题

### Q: 部署后页面空白？
A: 检查浏览器控制台(F12)是否有404错误，确认资源路径是否正确

### Q: 图片加载失败？
A: 确保图片使用 HTTPS 链接，或放在项目目录中通过相对路径引用

### Q: 如何绑定国内域名？
A: 在 Cloudflare 添加域名后，需要：
1. 在域名注册商处修改 DNS 为 Cloudflare 提供的地址
2. 在 Cloudflare DNS 设置中添加 CNAME 记录指向你的 Pages 域名
3. 等待 DNS 生效（通常几分钟到几小时）

### Q: 免费版有什么限制？
- 每月 500 次构建
- 无限请求次数
- 无限带宽
- 适合个人和小型项目

## 联系方式

如有问题，可在 GitHub Issues 中提交反馈。
