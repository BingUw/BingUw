# 如何把炫酷主页挂到 GitHub

## 1. 建「个人主页仓库」

- 仓库名必须是：**BingUw**（与用户名完全一致，区分大小写）
- 设为 **Public**
- 不要用 README 模板也行，后面覆盖即可

## 2. 上传本目录内容

把本文件夹里的内容推送到 `BingUw` 仓库根目录（至少包含 `README.md`）。

## 3. 贡献蛇动画（可选，需 `workflow` 权限的 Token 或网页创建）

若用 **git push** 推送含 `.github/workflows/*.yml` 的文件，Personal Access Token 需勾选 **`workflow`** 范围，否则会推送失败。

**方式 A（推荐）**：在 GitHub 网页 **Add file → Create new file**，路径填 `.github/workflows/snake.yml`，粘贴以下内容并提交：

```yaml
name: Generate contribution snake

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

permissions:
  contents: write

jobs:
  snake:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/github-contribution-grid-snake.svg
      - uses: crazy-max/ghaction-github-pages@v4
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

然后在 **README.md** 里取消「Contribution snake」那一段的 HTML 注释，并推送 README。

**方式 B**：本地 Token 勾选 `workflow` 后，再 `git push` 包含该 workflow 的提交。

仓库 **Settings → Actions → General** 允许 Actions 后，在 **Actions** 里手动 **Run workflow**。生成 **`output`** 分支后蛇图链接才有效。

若不需要蛇图：保持 README 里蛇图段落为注释即可。

## 4. 自定义

- 改 `README.md` 里的学校链接、研究方向、徽章（TensorFlow / JS 等可删可换）
- 统计卡片使用 [Rickstaa 镜像](https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/)：官方 `github-readme-stats.vercel.app` 常因 **Vercel 部署暂停** 出现 503，故已改用镜像；若将来镜像也失效，可自行 [fork 部署](https://github.com/anuraghazra/github-readme-stats) 或使用 [官方推荐的 GitHub Action 生成 SVG](https://github.com/marketplace/actions/github-readme-stats-action)。
- 连续贡献图请使用 **`streak-stats.demolab.com`**，旧域名 `github-readme-streak-stats.demolab.com` 可能无法加载。

访问你的主页：<https://github.com/BingUw>
