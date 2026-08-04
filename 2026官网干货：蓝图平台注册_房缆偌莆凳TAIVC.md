蓝图平台注册【Q-——333307——】蓝图平台注册【 辋芷《888yx●vip》 】
蓝图平台注册【Q-——333307——】蓝图平台注册【 辋芷《888yx●vip》 】

 用 Python 写一个简易版 GitHub Trending 爬虫，每天自动抓取热门仓库

作为一个经常刷 GitHub 找开源项目的人，我几乎每天早上都会打开 Trending 页面看看今天有什么新东西。但每次都要打开浏览器、手动翻页，久而久之有点烦——于是干脆写了个小爬虫，下班前跑一遍，把结果推送到微信，睡前扫一眼就够了。

这篇不整花活，直接讲怎么用 Python + Requests + BeautifulSoup 写一个稳定能跑的 GitHub Trending 爬虫，并给出适合收录和二次开发的结构。

 一、核心思路：Trending 页面是静态 HTML，抓取难度低

GitHub Trending 的页面源码里直接包含仓库名、描述、星标数和今日新增星标，不用调用 API 也没有登录限制。所以抓取流程可以简化为三步：

1. 用 Requests 带 User-Agent 请求 `https://github.com/trending`（默认抓当日，也可以加 `/python` 等语言后缀）。
2. 用 BeautifulSoup 定位 `article.Box-row` 这个重复节点，逐个提取仓库信息。
3. 清洗数据（去掉多余空白、拼接作者/仓库名），保存到 JSON 或 CSV。

 二、关键代码段：30 行搞定核心抓取

```python
import requests
from bs4 import BeautifulSoup

headers = {"User-Agent": "Mozilla/5.0\

相关推荐：

https://github.com/klinegina28/bhjqeg/blob/main/2026%E6%9D%83%E5%A8%81%E7%94%84%E9%80%89%EF%BC%9A%E8%93%9D%E5%9B%BE%E5%9C%B0%E5%9D%80%E4%B8%8B%E8%BD%BD_%E5%8F%82%E6%8E%B7%E4%B8%A5%E8%AF%96%E9%92%A1TNIJE.md

<img src="https://i.postimg.cc/9fTtX8xf/lantu-00003.png" />

相关推荐：

https://github.com/klinegina28/bhjqeg/commit/b88d70900e2079129baaa9de29194f902de07f08

<img src="https://i.postimg.cc/rsg9XDf0/lantu-00001.png" />
相关推荐：

https://github.com/brownbarbara40/yzuprm/blob/main/2026%E5%AE%98%E6%96%B9%E5%A4%8D%E7%9B%98%EF%BC%9A%E8%93%9D%E5%9B%BE%E7%BD%91%E5%9D%80%E5%A8%B1%E4%B9%90_%E8%B0%98%E5%A4%B4%E9%85%AA%E5%86%92%E5%80%8FHICXK.md

<img src="https://i.postimg.cc/9fTtX8xf/lantu-00003.png" />
相关推荐：

https://github.com/brownbarbara40/yzuprm/commit/b7f90a0562db5fc7fea1c528590735f60a220dc8

<img src="https://i.postimg.cc/kGjWYk5W/lantu-00006.png" />

资讯来源：新华网、人民网、央视新闻、中新网、凤凰网、澎湃新闻、界面新闻、新浪新闻、搜狐网、财新网、观察者网、第一财经等主流平台，以独树一帜的观察视角与扎实的深度报道能力，在资讯领域收获广泛关注。
