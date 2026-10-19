# 太原 Kindle 墨水屏看板

为 Kindle Paperwhite 4 制作的纯静态网页，不需要越狱。

在线地址：<https://wangyao5451-glitch.github.io/kindle-paperwhite-dashboard/>

## 内容

- 当前时间、公历日期、星期与农历
- 太原实时天气、体感温度、湿度和风速
- 未来四日天气与降雨概率
- 每日语录
- 当月月历
- 横屏与竖屏自动切换的两套排版
- 全页面纯白背景，保留适合墨水屏的黑色文字与线条
- 天气缓存；临时断网时保留上一次成功结果

## 本地预览

不要直接双击 `index.html` 测试天气，因为部分浏览器会限制本地文件联网。请在本目录启动一个静态服务器：

```powershell
python -m http.server 8080
```

然后访问 `http://localhost:8080/`。

## 发布到 GitHub Pages

1. 新建一个 GitHub 仓库。
2. 将本目录中的全部文件上传到仓库根目录。
3. 打开仓库 `Settings → Pages`。
4. 在 `Build and deployment` 中选择 `Deploy from a branch`，选择 `main` 和 `/ (root)`。
5. 等待 GitHub 给出 `https://用户名.github.io/仓库名/` 地址。
6. 在 Kindle 浏览器打开该网址并添加书签。

如果 Kindle 无法打开 GitHub Pages 或无法读取天气，通常是旧版浏览器的 HTTPS/TLS 兼容问题。此时可把相同文件放在家中电脑、NAS 或路由器的静态服务器上，通过局域网 HTTP 地址访问。

## Kindle 使用

- 在 Kindle 的显示或浏览器菜单中切换横竖方向后，页面会根据可用区域自动改用横版或竖版排版。
- 网页本身无法在不越狱的条件下强制改变 Kindle 的系统屏幕方向。
- “刷新”按钮会立即重新获取天气。
- 天气默认每 15 分钟更新一次。
- 城市坐标固定为太原市中心附近（北纬 37.8706°、东经 112.5489°）。

## 文件

- `index.html`：页面、样式与天气逻辑
- `solarlunar.js`：农历转换库
- `LICENSE-solarlunar.txt`：农历转换库许可证

天气数据来自 Open-Meteo。农历转换使用 `solarlunar` 2.0.7（ISC License）。
