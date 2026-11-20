# 部署到 GitHub Pages

本站点是纯静态 HTML/CSS，无构建步骤、无依赖包。仓库 `GeniusORC/GeniusORC.github.io` 位于 `main` 分支。

## 1. 本地预览

```bash
cd GeniusORC.github.io
python3 -m http.server 8000
```

浏览器打开 <http://localhost:8000>。预览完成后按 `Ctrl+C` 停止。

## 2. 提交并推送到 GitHub

```bash
cd GeniusORC.github.io
git status
git add .
git commit -m "Build academic homepage"
git push origin main
```

若尚未配置 Git 身份，先执行：

```bash
git config --local user.name "Your Name"
git config --local user.email "your.email@example.com"
```

## 3. 开启 GitHub Pages

1. 打开 <https://github.com/GeniusORC/GeniusORC.github.io/settings/pages>
2. **Build and deployment** → **Source** 选择 **Deploy from a branch**
3. **Branch** 选择 `main`，目录选择 **/(root)**
4. 点击 **Save**
5. 等待 1–2 分钟，页面右上角出现 “Your site is live at …” 即部署成功

## 4. 访问地址

仓库名 `GeniusORC.github.io` 与账号名 `GeniusORC` 一致，因此这是用户站点，部署后的地址为：

<https://geniusorc.github.io/>

## 5. 后续更新

修改 `index.html` 或 `assets/` 后重复第 2 步；GitHub Pages 通常在推送后 1–2 分钟内更新。若浏览器仍显示旧版本，使用强制刷新（`Cmd+Shift+R` / `Ctrl+F5`）或开启无痕窗口验证。

## 6. 可选：自定义域名

在仓库根目录新建 `CNAME` 文件，内容为你的域名（例如 `www.example.com`），在域名注册商处将 CNAME 指向 `geniusorc.github.io`，并在 Pages 设置中填写同一域名。使用自定义域名时不要混用 `www` 与非 `www`，否则需要分别配置。

## 7. 故障排查

- 页面 404：确认 Pages 分支为 `main`、目录为 `/(root)`，且 `index.html` 位于仓库根目录。
- 样式异常：确认 `assets/profile.svg` 已推送。
- 推送被拒绝：先执行 `git pull --rebase origin main` 再推送。
- 本地预览正常但线上异常：检查仓库是否为私有仓库；免费账户的 GitHub Pages 要求仓库公开。
