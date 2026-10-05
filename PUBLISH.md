# 发布清单 / Publishing checklist

1. **改名字** / Rename: replace `your-github-username` in `package.json` (repository url), `README.md`, and rename `../data/plugins/your-github-username__dsh-bliss-glass.yml` accordingly.
2. **建仓库** / Create a public GitHub repo named `dsh-bliss-glass`, push this folder as the repo root:
   ```sh
   git init && git add -A && git commit -m "Bliss Glass v1.0.0"
   git remote add origin https://github.com/<owner>/dsh-bliss-glass.git
   git push -u origin main
   ```
3. **加 topic** / Add the `dsh-plugin` topic in the repo settings.
4. **截图** / Screenshots: drop 3 images into `assets/` — light mode, dark mode, the picker menu open — named as `screenshots.json` expects.
5. **等 1 天** / Wait: the list's CI checks that the repo is at least 1 day old.
6. **（可选）预构建包** / Optional prebuilt tarball (storefronts prefer it):
   ```sh
   git archive --format=tgz -o dsh-bliss-glass.tgz HEAD
   ```
   Attach `dsh-bliss-glass.tgz` to a GitHub Release (the yml's `tarball:` line already points at `latest/download`). If you skip this, delete the `tarball:` line from the yml — the plugin installs from source just fine.
7. **投稿** / Fork [awesome-dsh-plugin](https://github.com/awesome-dsh-plugin/awesome-dsh-plugin), copy `data/plugins/<owner>__dsh-bliss-glass.yml` into your fork, open a PR. Category is `theme`, so it lands in the dsh-market **Themes** tab automatically.
8. 合并后网站与市场自动重建；用户从主题分类一键安装。
