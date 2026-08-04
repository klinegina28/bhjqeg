蓝图网址登录【Q-——333307——】蓝图网址登录【 辋芷《888yx●vip》 】
蓝图网址登录【Q-——333307——】蓝图网址登录【 辋芷《888yx●vip》 】

 从零搭建个人博客：GitHub Pages + Hexo 完整教程

作为一名开发者，拥有一个专属的技术博客，不仅是记录成长的方式，更是打造个人品牌、沉淀知识体系的绝佳途径。而利用 GitHub Pages 搭配 Hexo 框架，则是目前最流行、零成本且高度可定制的解决方案。

本文将带你从零开始，完成本地环境搭建、站点配置到一键部署的全流程。

 一、为什么选择 Hexo + GitHub Pages？

- 免费与稳定：托管在 GitHub 上，无需购买服务器，全球访问速度快。
- 极速构建：Hexo 基于 Node.js，生成静态页面毫秒级完成。
- 主题丰富：社区拥有大量精美主题，支持高度自定义，满足极简或炫酷需求。
- SEO 友好：纯静态输出，对搜索引擎爬虫极其友好，利于文章收录。

 二、部署前必备工具与准备

在开始前，请确保你的电脑已安装以下环境：

1.  Node.js （建议 LTS 版本）：用于运行 Hexo 脚手架。
2.  Git ：用于版本控制及代码推送。
3.  GitHub 账号：用于创建远程仓库。

> 小贴士：若网络不畅，可提前配置 npm 淘宝镜像源，加速依赖下载。

 三、本地快速搭建 Hexo 框架

打开终端（命令行），执行以下三步曲：

```bash
 1. 全局安装 Hexo 命令行工具
npm install -g hexo-cli

 2. 初始化博客目录（blog 为你想要的文件夹名）
hexo init blog

 3. 进入目录并安装依赖
cd blog
npm install
```

安装完成后，运行 `hexo s`，浏览器访问 `http://localhost:4000`，即可看到默认的 Hello World 页面。

 四、关联 GitHub 并部署上线

1.  新建仓库：在 GitHub 上新建一个仓库，命名为 `你的用户名.github.io`（必须完全一致）。
2.  安装部署插件：在博客根目录运行 `npm install hexo-deployer-git --save`。
3.  修改配置：打开根目录下的 `_config.yml`，在末尾 `deploy` 区域修改如下：

```yaml
deploy:
  type: git
  repo: https://github.com/你的用户名/你的用户名.github.io.git
  branch: main
```

4.  一键部署：依次执行 `hexo clean`、`hexo g`、`hexo d`。

此时，在浏览器输入 `https://你的用户名.github.io`，你的博客就已正式上线啦！

 五、日常写作与更新指南

写新文章非常简单：

```bash
hexo new "我的第一篇文章"
```

Markdown 文件生成于 `source/_posts` 目录，编辑保存后，重复执行 `hexo g -d` 即可完成发布。

内容建议：专注于技术干货、踩坑记录或项目复盘，保持高频更新，能显著提升搜索引擎的抓取频率。

---

互动引导：如果你在部署过程中遇到任何报错，或想了解如何更换炫酷主题，欢迎在评论区留言或私信我，我会第一时间为你解答！也别忘了把这篇干货分享给身边需要的朋友。

关注我，后续将带来更多关于性能优化与自动化部署的深度教程。

相关推荐：

https://github.com/brownbarbara40/yzuprm/blob/main/2026%E5%AE%98%E7%BD%91%E8%AE%BF%E8%B0%88%EF%BC%9A%E8%93%9D%E5%9B%BE%E5%AE%98%E7%BD%91%E4%B8%8B%E8%BD%BD_%E9%A9%B6%E6%9E%97%E6%B4%9E%E9%A2%88%E8%90%84XVCJK.md

<img src="https://i.postimg.cc/50y4qGDp/lantu-00014.png" />

相关推荐：

https://github.com/brownbarbara40/yzuprm/commit/b7cd1131f6bf5a713efa12b59e54156307531d38

<img src="https://i.postimg.cc/T2Zb1qDM/lantu-00015.png" />
相关推荐：

https://github.com/singhcourtney93/oormzh/blob/main/%E5%85%B1%E8%B5%B4%E6%96%87%E5%8C%96%E4%B9%8B%E7%BA%A6%EF%BC%9A%E8%93%9D%E5%9B%BE%E5%BC%80%E6%88%B7%E6%B3%A8%E5%86%8C_%E5%B9%BD%E6%9F%BF%E6%95%85%E9%95%AD%E6%97%A8BOVWP.md

<img src="https://i.postimg.cc/FsWxTJds/lantu-00002.png" />
相关推荐：

https://github.com/singhcourtney93/oormzh/commit/6d55bfa2bd4f061bfc159c91df8901f2b580630f

<img src="https://i.postimg.cc/T2Zb1qDM/lantu-00015.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
