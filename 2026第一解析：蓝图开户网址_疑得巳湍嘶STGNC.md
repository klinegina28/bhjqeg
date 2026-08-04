蓝图开户网址【Q-——333307——】蓝图开户网址【 辋芷《888yx●vip》 】
蓝图开户网址【Q-——333307——】蓝图开户网址【 辋芷《888yx●vip》 】

 用GitHub Actions自动化部署Hexo博客，一键搞定发布流程（附YAML配置）

还在手动`hexo g`然后`hexo d`？每次发布都重复操作，费时又容易出错。今天分享一个自动化部署方案，用GitHub Actions把发布流程全部接管，push代码后自动生成静态文件并部署到Pages，省心省力。

 为什么推荐GitHub Actions？

GitHub Actions是GitHub自带的CI/CD工具，无需额外服务器，配置简单，免费额度对于个人博客完全够用。配合Hexo，能实现从源码推送到自动构建、自动部署的完整闭环。

 核心配置步骤

 1. 准备工作
在GitHub仓库中，进入Settings → Secrets and variables → Actions，添加以下密钥：
- `GITHUB_TOKEN`（系统默认，无需手动添加）
- `HEXO_DEPLOY_KEY`（在部署分支的Deploy keys中生成）

 2. 编写工作流文件
在项目根目录创建`.github/workflows/deploy.yml`，内容如下：

```yaml
name: Hexo Deploy

on:
  push:
    branches: [ main ]

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
        with:
          submodules: recursive

      - name: Setup Node
        uses: actions/setup-node@v3
        with:
          node-version: '18'

      - name: Install & Build
        run: |
          npm install
          npx hexo clean
          npx hexo generate

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          personal_token: ${{ secrets.HEXO_DEPLOY_KEY }}
          publish_dir: ./public
          publish_branch: gh-pages
```

 3. 配置站点`_config.yml`
确保部署配置指向正确的仓库地址：

```yaml
deploy:
  type: git
  repo: git@github.com:你的用户名/你的仓库.git
  branch: gh-pages
```

 常见问题排查

构建失败但本地正常？ 检查Node版本是否一致，建议锁定`package.json`中的依赖版本。

部署后页面空白？ 确认`_config.yml`中的`root`路径是否正确，特别是使用项目Pages时需设置为`/仓库名/`。

 效率提升小技巧

- 在Actions页面可以查看每次构建的日志，问题定位非常方便
- 配合`dependabot`自动更新依赖，减少手动维护成本
- 使用`concurrency`配置避免多任务并发冲突

这套流程配置一次后，以后每次写文章只需push，剩下都交给Action处理。如果觉得有用，欢迎Star收藏，也欢迎在评论区交流你在使用中遇到的问题。你的支持是我持续分享的动力！

相关推荐：

https://github.com/jarvisdanielle312/mphvpi/blob/main/2026%E7%AC%AC%E4%B8%80%E6%80%BB%E7%BB%93%EF%BC%9A%E4%B9%90%E5%AF%8C%E5%AE%98%E7%BD%91%E7%BD%91%E5%9D%80_%E9%99%A8%E7%87%83%E8%95%BE%E6%A1%88%E5%BB%B6HNOWV.md

<img src="https://i.postimg.cc/T2Zb1qDM/lantu-00015.png" />

相关推荐：

https://github.com/jarvisdanielle312/mphvpi/commit/194284c31aaf740674284cf14489d00403606aaa

<img src="https://i.postimg.cc/sfKP2ZJh/lantu-00007.png" />
相关推荐：

https://github.com/martinezjessica6229/eyvqwl/blob/main/%E6%96%87%E5%A8%B1%E8%A1%8C%E4%B8%9A%E5%8A%A8%E6%80%81%EF%BC%9A%E4%B9%90%E5%AF%8C%E5%AE%98%E7%BD%91%E5%B9%B3%E5%8F%B0_%E5%87%A0%E5%83%AD%E4%BB%9D%E6%B2%83%E5%A5%84PXYIK.md

<img src="https://i.postimg.cc/sfKP2ZJh/lantu-00007.png" />
相关推荐：

https://github.com/martinezjessica6229/eyvqwl/commit/15d32aff6810d10599483f8548dd5c9d5e40a47d

<img src="https://i.postimg.cc/9fTtX8xf/lantu-00003.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
