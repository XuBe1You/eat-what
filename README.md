# 等会儿吃啥？

一个转盘随机选餐的小网页。把自己常吃的店或菜加进菜单，点中间的「抽」，转盘停下来就是今天的答案。

纯静态、单文件、不联网、不上传任何数据——菜单存在你自己浏览器的 `localStorage` 里。

## 用起来

1. 打开 [`index.html`](index.html)（或线上地址）。
2. 在「我的菜单」里填店名或菜名，链接是选填项；填了就跳转。
3. 点中间的「抽」。

最多 10 个选项，至少 2 个。支持增删、恢复默认、全部清空，改动即时保存。

## 本地跑

不需要构建，也不需要 Node：

```bash
# 直接双击 index.html 也行；想用本地服务器：
python -m http.server 8000
# 打开 http://localhost:8000
```

## 部署

整个目录就是站点根目录，扔到任何静态托管都能跑：

- **GitHub Pages**：仓库 Settings → Pages → Source 选 `main` 分支 `/` 根目录。
- **Cloudflare Pages / EdgeOne Pages**：无构建命令，输出目录填 `/`。

国内访问 `github.io` 不太稳定，长期用建议换 Cloudflare Pages 或绑定自己的域名。

## 改配色

`index.html` 顶部的 `:root` 里四个变量是整站的色板，`.PALETTE` 数组控制扇形颜色：

```js
var PALETTE = ["#ffd3e7", "#ffe24b", "#c8f04a", "#cfe0ff", "#ffd9a8", "#e6dcff"];
```

## 开源协议

- 本页面的代码：MIT，见 [LICENSE](LICENSE)。
- 转盘库 [lucky-canvas](https://github.com/buuing/lucky-canvas)：Apache-2.0，见 [NOTICE](NOTICE)。`lucky.umd.js` 是它构建好的 UMD 文件，直接内嵌在仓库里，不依赖 CDN。
