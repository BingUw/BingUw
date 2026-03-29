# 如何把炫酷主页挂到 GitHub

## 1. 建「个人主页仓库」

- 仓库名必须是：**BingUw**（与用户名完全一致，区分大小写）
- 设为 **Public**
- 不要用 README 模板也行，后面覆盖即可

## 2. 上传本目录内容

把本文件夹里的内容推送到 `BingUw` 仓库根目录：

- `README.md` → 根目录
- `.github/workflows/snake.yml` → 同上路径（用于贡献蛇动画）

## 3. 开启 Actions（若要蛇图）

仓库 **Settings → Actions → General**，允许 Actions。  
打开 **Actions** 标签，选中 **Generate contribution snake**，点 **Run workflow**。  
成功后会出现 `output` 分支，README 里的蛇图链接才会生效。

若不需要蛇图：删除 README 里「Contribution snake」整段，并可删掉 `.github/workflows/snake.yml`。

## 4. 自定义

- 改 `README.md` 里的学校链接、研究方向、徽章（TensorFlow / JS 等可删可换）
- 统计图来自 [github-readme-stats](https://github.com/anuraghazra/github-readme-stats)，若加载慢可换主题或自建

访问你的主页：<https://github.com/BingUw>
