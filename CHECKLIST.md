# Cloudflare Pages 部署检查清单

## 部署前检查

- [ ] 所有 HTML/CSS/JS 文件已保存
- [ ] 本地浏览器测试通过（打开 index.html 正常显示）
- [ ] 图片链接可正常加载
- [ ] 评论区功能正常
- [ ] 各版块切换正常

## GitHub 上传

- [ ] 已注册 GitHub 账号
- [ ] 已创建公开仓库 `techgeek-hub`
- [ ] 已将所有文件推送到 main 分支
- [ ] GitHub 仓库页面显示所有文件

## Cloudflare 配置

- [ ] 已注册/登录 Cloudflare
- [ ] 已授权 Cloudflare 访问 GitHub
- [ ] 已选择 `techgeek-hub` 仓库
- [ ] Framework preset 设为 `None`
- [ ] Build command 留空
- [ ] Build output directory 设为 `/`
- [ ] 点击 Save and Deploy

## 部署后验证

- [ ] Cloudflare Pages 显示 "Build successful"
- [ ] 访问 `xxx.pages.dev` 域名正常显示
- [ ] 首页轮播图正常
- [ ] 各版块导航正常
- [ ] 评论区可正常发表评论
- [ ] 图片可正常预览
- [ ] 移动端响应式正常

## 可选：自定义域名

- [ ] 已购买/拥有域名
- [ ] 在 Cloudflare 添加自定义域名
- [ ] DNS 记录配置正确
- [ ] SSL 证书已颁发
- [ ] 通过自定义域名可正常访问
