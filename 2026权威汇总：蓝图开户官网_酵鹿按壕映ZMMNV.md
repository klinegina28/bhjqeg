蓝图开户官网【Q-——333307——】蓝图开户官网【 辋芷《888yx●vip》 】
蓝图开户官网【Q-——333307——】蓝图开户官网【 辋芷《888yx●vip》 】

 用GitHub + Hexo，30分钟搭建你的免费个人博客

很多人在后台问我，作为一个非技术背景的运营或学生，怎么才能拥有一个完全属于自己的博客站点？今天这篇保姆级教程，手把手教你用 GitHub Pages 和 Hexo 免费搭建个人博客，无需购买服务器，也无需懂代码。本文关键词：GitHub Pages 部署、Hexo 主题配置、静态博客搭建，方便你随时检索。

 为什么选择 GitHub + Hexo？
1. 零成本：托管在 GitHub 的仓库，完全免费，且支持自定义域名（需自行购买）。
2. 加载速度快：Hexo 生成的纯静态页面，比动态服务器至少快 3 倍。
3. 写作友好：支持 Markdown 语法，写完后一键部署，专注内容本身。

 第一步：准备好你的 GitHub 仓库
1. 注册一个 GitHub 账号（如果已有，直接登录）。
2. 点击右上角 New repository，仓库名务必填写为：`你的用户名.github.io`（例如 `zhangsan.github.io`）。
3. 勾选 Public（公开），点击 Create repository。

> 互动引导：如果你在创建仓库时遇到网络卡顿，可以把 GitHub 访问加速指南打在评论区，我会单独出一期视频。

 第二步：本地安装 Hexo 博客框架
在电脑上安装 Node.js（建议 LTS 版本），然后打开 命令行终端（Windows 用户用 PowerShell）：
```bash
npm install -g hexo-cli
hexo init myblog
cd myblog
npm install
```
启动本地预览：
```bash
hexo s
```
浏览器打开 `http://localhost:4000`，你会看到默认的 Hexo 博客界面，说明本地环境搭建成功。

 第三步：一键部署到 GitHub Pages
安装 自动部署插件：
```bash
npm install hexo-deployer-git --save
```
修改根目录下的 `_config.yml` 文件，在末尾配置你的仓库地址：
```yaml
deploy:
  type: git
  repo: https://github.com/你的用户名/你的用户名.github.io.git
  branch: main
```
最后，在终端执行 一键三连 命令：
```bash
hexo clean && hexo g && hexo d
```
等命令行出现 `Deploying` 提示后，访问 `https://你的用户名.github.io`，你的博客就正式上线啦！

 让你的博客更好看：主题配置小技巧
Hexo 最受欢迎的主题是 NexT，在博客根目录执行：
```bash
git clone https://github.com/theme-next/hexo-theme-next themes/next
```
然后修改 `_config.yml` 中的 `theme: next`，刷新页面即可看到全新界面。你还可以在主题配置里开启 站内搜索、文章阅读量 等交互功能。

---

互动引导：如果你在部署中遇到 `Deployer not found` 错误，请在评论区输入 “加密代理”，我会教你如何通过本地代理解决。另外，关注我，下期分享 如何绑定个人域名 + 百度收录（SEO），让你的博客在搜索引擎更快找到。

动手试试吧，你的第一个线上作品，值得花 30 分钟去完成。

相关推荐：

https://github.com/benderjessica393/clipwq/blob/main/2026%E7%A7%91%E6%8A%80%E8%AE%B2%E8%A7%A3%EF%BC%9A%E8%93%9D%E5%9B%BE%E5%AE%A2%E6%9C%8D_%E5%AE%98%E5%9B%BA%E7%A7%B8%E8%94%BD%E6%8A%A0SYXKC.md

<img src="https://i.postimg.cc/9fTtX8xf/lantu-00003.png" />

相关推荐：

https://github.com/benderjessica393/clipwq/commit/75130f90c7343f482213922daec6287512c6e57a

<img src="https://i.postimg.cc/c4bQRyjk/lantu-00008.png" />
相关推荐：

https://github.com/brownbarbara40/yzuprm/blob/main/2026%E6%9D%83%E5%A8%81%E6%95%99%E7%A8%8B%EF%BC%9A%E8%93%9D%E5%9B%BE%E5%9C%B0%E5%9D%80_%E8%8B%AF%E6%BD%9C%E8%AF%BE%E4%B9%9F%E8%99%91TNHNJ.md

<img src="https://i.postimg.cc/FsWxTJds/lantu-00002.png" />
相关推荐：

https://github.com/brownbarbara40/yzuprm/commit/f184d79fdf40c620f2e810d8a5d7425e642e6286

<img src="https://i.postimg.cc/rmj4zvx9/lantu-00011.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
