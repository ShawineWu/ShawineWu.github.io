# ShawineWu 个人博客

基于 [Hexo](https://hexo.io/) 的静态博客，部署到 GitHub Pages。

## 环境要求

- Node.js 18+
- npm 或 pnpm

## 本地开发

```bash
# 安装依赖（首次或更新后）
npm install

# 启动本地预览（默认 http://localhost:4000）
npm run server
```

## 常用命令

| 命令 | 说明 |
|------|------|
| `npm run server` | 启动本地服务器并监听文件变化 |
| `npm run build` | 生成静态文件到 `public/` |
| `npm run clean` | 清除缓存和生成文件 |
| `npm run deploy` | 生成并部署到 GitHub Pages |

## 写文章

- 文章放在 `source/_posts/`，使用 Markdown。
- 新建文章：`npx hexo new post "文章标题"`
- 新建页面：`npx hexo new page "页面名称"`

## 部署到 GitHub Pages（GitHub Actions）

本项目使用 [GitHub Actions](https://hexo.io/zh-cn/docs/github-pages) 自动部署：推送源码到 `main` 后自动构建并发布，无需本地执行 `hexo deploy`。

**首次部署前请完成：**

1. 在仓库 **Settings → Pages** 中：
   - **Source** 选择 **GitHub Actions**，保存。

2. 将本地代码推送到默认分支（通常为 `main`）：

   ```bash
   git add .
   git commit -m "Deploy with GitHub Actions"
   git push -u origin main
   ```

3. 推送后到 **Actions** 页查看工作流运行情况，成功后访问 **https://ShawineWu.github.io** 即可。

之后每次 `git push` 到 `main` 都会自动重新构建并更新站点。工作流配置见 `.github/workflows/pages.yml`。

## 主题与结构

当前使用 [hexo-theme-reimu](https://github.com/D-Sketon/hexo-theme-reimu)（博丽灵梦风格）。

- **站点配置**：根目录 `_config.yml`（标题、作者、URL、部署等）
- **主题配置**：主题通过 npm 安装，默认配置在 `node_modules/hexo-theme-reimu/_config.yml`。若需深度自定义，可将主题克隆到 `themes/reimu` 后修改该文件。

Reimu 所需目录（已创建）：

- `source/_data/avatar/`：放头像，默认文件名 `avatar.webp`
- `source/_data/covers.yml`、`source/_data/covers/`：文章封面（可选）
- `source/about/index.md`：关于页
- `source/friend/index.md`、`source/friend/_data.yml`：友链页及数据

站点地址：**https://ShawineWu.github.io**
