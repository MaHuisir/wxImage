# 部署指南

## 🚀 快速部署到 Netlify

### 方式一：拖拽部署（推荐，最快）

1. **访问 Netlify Drop**
   - 打开 https://app.netlify.com/drop
   - 或登录 Netlify 后点击 "New site" → "Deploy manually"

2. **拖拽文件夹**
   - 将整个 `朋友圈照片画质提高` 文件夹拖拽到页面
   - 等待上传完成（通常 10-30 秒）

3. **获取链接**
   - 部署完成后，你会得到一个公开链接
   - 例如：`https://moments-magic-xyz.netlify.app`
   - 可以立即分享使用！

### 方式二：Git 连接（推荐，便于更新）

1. **推送到 GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/moments-magic.git
   git push -u origin main
   ```

2. **在 Netlify 连接**
   - 登录 https://app.netlify.com
   - 点击 "New site from Git"
   - 选择 GitHub，授权并选择仓库
   - 点击 "Deploy site"

3. **自动部署**
   - 每次 push 到 main 分支时自动部署
   - 可以在 Netlify 仪表板查看部署状态

### 方式三：Netlify CLI（开发者推荐）

1. **安装 Netlify CLI**
   ```bash
   npm install -g netlify-cli
   ```

2. **登录**
   ```bash
   netlify login
   ```

3. **部署**
   ```bash
   cd 朋友圈照片画质提高
   netlify deploy --prod
   ```

## 📋 部署前检查清单

- [ ] 所有文件都在同一文件夹中
- [ ] `index.html` 在根目录
- [ ] `netlify.toml` 配置正确
- [ ] 本地测试无误（用浏览器打开 index.html）

## 🔧 部署后配置

### 自定义域名
1. 在 Netlify 仪表板 → Site settings → Domain management
2. 点击 "Add custom domain"
3. 输入你的域名（需要先在域名注册商配置 DNS）

### 环境变量（如需要）
1. Site settings → Build & deploy → Environment
2. 添加环境变量（本项目不需要）

### 构建设置
- **Build command**: 留空（无需构建）
- **Publish directory**: `.`（当前目录）

## 🌐 域名配置（可选）

如果你有自己的域名，可以绑定到 Netlify：

1. **在域名注册商配置 DNS**
   - 添加 CNAME 记录指向 Netlify 提供的地址
   - 或使用 Netlify DNS（更简单）

2. **在 Netlify 配置**
   - Site settings → Domain management
   - 添加自定义域名
   - 按照提示完成 DNS 配置

## 📊 监控和分析

### 查看部署状态
- Netlify 仪表板 → Deploys
- 查看每次部署的日志和状态

### 性能监控
- Netlify Analytics（付费功能）
- 或使用 Google Analytics（免费）

### 错误追踪
- Netlify Functions 日志
- 浏览器开发者工具

## 🆘 常见问题

### Q: 部署后页面显示 404？
A: 检查 `netlify.toml` 中的重定向规则是否正确

### Q: 图片压缩不工作？
A: 检查浏览器是否支持 Canvas API（所有现代浏览器都支持）

### Q: 如何更新已部署的网站？
A: 
- 如果用 Git 连接：直接 push 到 GitHub，Netlify 自动部署
- 如果用拖拽部署：重新拖拽新文件夹

### Q: 可以添加后端吗？
A: 可以使用 Netlify Functions 添加无服务器函数

## 🚀 性能优化建议

1. **启用 Gzip 压缩**
   - Netlify 默认启用

2. **启用缓存**
   - 在 `netlify.toml` 中配置缓存头

3. **CDN 加速**
   - Netlify 自动使用全球 CDN

## 📞 获取帮助

- Netlify 文档：https://docs.netlify.com
- Netlify 社区：https://community.netlify.com
- GitHub Issues：提交问题

---

**祝部署顺利！🎉**
