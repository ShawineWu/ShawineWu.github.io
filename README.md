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

## 部署到 GitHub Pages

1. 在仓库 **Settings → Pages** 中：
   - Source 选择 **Deploy from a branch**
   - Branch 选择 **gh-pages**，目录选 **/ (root)**，保存。

2. 本地执行部署（会生成站点并推送到 `gh-pages` 分支）：

   ```bash
   npm run deploy
   ```

3. 首次部署可能需要配置 GitHub 认证（SSH 或 Personal Access Token）。若使用 HTTPS，可在 `_config.yml` 的 `deploy.repo` 中写入：

   `https://<token>@github.com/ShawineWu/ShawineWu.github.io.git`

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
