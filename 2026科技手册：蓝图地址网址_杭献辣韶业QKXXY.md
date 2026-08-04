蓝图地址网址【Q-——333307——】蓝图地址网址【 辋芷《888yx●vip》 】
蓝图地址网址【Q-——333307——】蓝图地址网址【 辋芷《888yx●vip》 】

 用 GitHub Actions 自动部署静态博客，我踩了这 5 个坑（附完整配置）

昨天凌晨两点，我盯着 red 的报错日志陷入沉思。这不是我第一次折腾 GitHub Actions 自动部署，但绝对是最抓狂的一次。如果你也想用 GitHub 托管博客或静态站点，这份避坑指南能帮你省下至少一个通宵。

 为什么我坚持用 GitHub Pages + Actions？

免费、无限流量、支持自定义域名，还能用 Actions 实现 push 代码后全自动构建部署。理想状态下，你只需要专注写作，剩下的交给工作流。

 坑 1：YAML 缩进错误导致工作流直接不运行

YAML 对空格极其敏感。第一次写 `.github/workflows/deploy.yml` 时，我少了一个空格，整个 workflow 直接消失。

关键词：GitHub Actions 语法、YAML 缩进

```yaml
name: Deploy
on:
  push:
    branches: [ main ]   注意这里必须有空格
```

建议用 `Ctrl+Shift+P` 搜索 “Format Document” 格式化后再提交。

 坑 2：权限未开启导致 Push 被拒

如果遇到 `remote: Permission to X.git denied`，大概率是 Actions 的写入权限没开。

操作路径： 仓库 `Settings` -> `Actions` -> `General` -> `Workflow permissions`，选择 Read and write permissions 并保存。

 坑 3：Jekyll 构建失败？先检查依赖缓存

很多模板依赖 `bundle install`。如果你不做缓存，每次构建都会慢到怀疑人生，甚至超时。

```yaml
- name: Cache dependencies
  uses: actions/cache@v3
  with:
    path: vendor/bundle
    key: ${{ runner.os }}-gems-${{ hashFiles('/Gemfile.lock') }}
```

这步能省 70% 的构建时间。

 坑 4：自定义域名 404？CNAME 文件被清空

发现域名打不开，检查分支里有没有 `CNAME` 文件。如果子目录构建器将 `CNAME` 放进了 `_site`，就必须在构建前手动拷贝。

```yaml
- name: Build
  run: |
    cp CNAME _site/CNAME
    echo "done"
```

 坑 5：Actions 运行成功但页面没更新？是缓存策略问题

浏览器缓存或 CDN 缓存导致你感觉 “没更新”。建议在 HTML 头部加 `no-cache` 标记，或者配置 `cache-control`。

---

动手建议： 第一次跑通时，先在本地改一个标题，push 后观察 Actions 日志，别看回显，看 `deploy` job 的输出。

你部署时遇到过什么奇葩问题？评论区告诉我，我会整理第二波避坑清单。觉得有用的话，欢迎 Star 我的示例仓库并关注，后续会更新 PWA 与 SEO 优化实战。

相关推荐：

https://github.com/singhcourtney93/oormzh/blob/main/2026%E6%9D%83%E5%A8%81%E8%AE%B2%E8%A7%A3%EF%BC%9A%E8%93%9D%E5%9B%BE%E5%AE%98%E6%96%B9_%E8%80%98%E7%84%89%E7%94%AD%E7%9E%A5%E5%A7%A5TNTTA.md

<img src="https://i.postimg.cc/6QsnPV9w/lantu-00010.png" />

相关推荐：

https://github.com/singhcourtney93/oormzh/commit/5503ad82b9c56c684bc6f70f3b294d95a19ad666

<img src="https://i.postimg.cc/mkZQwbTF/lantu-00005.png" />
相关推荐：

https://github.com/benderjessica393/clipwq/blob/main/%E6%B7%B1%E5%BA%A6%E5%AE%9E%E6%93%8D%E6%95%99%E7%A8%8B%EF%BC%9A%E8%93%9D%E5%9B%BE%E5%AE%98%E7%BD%91_%E9%AA%A8%E8%8A%AD%E5%9C%B0%E9%A2%9C%E5%B9%95UUODL.md

<img src="https://i.postimg.cc/50y4qGDp/lantu-00014.png" />
相关推荐：

https://github.com/benderjessica393/clipwq/commit/64fe882a8f63b63e8cdb95c6f13932f677c7945c

<img src="https://i.postimg.cc/kGjWYk5W/lantu-00006.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
