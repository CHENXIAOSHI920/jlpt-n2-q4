# 上传到 GitHub Pages

这个文件夹就是可以直接上传的站点根目录。里面的 `index.html`、`manifest.webmanifest`、`sw.js` 和三个图标必须放在同一层。

## 方法一：网页上传（最简单）

1. 打开 GitHub，点右上角 `+` → `New repository`。
2. 仓库名可以填 `jlpt-n1-q4`，选择 `Public`，点 `Create repository`。
3. 在新仓库页面点 `Add file` → `Upload files`。
4. 把本文件夹里的全部文件拖进去（不要只拖文件夹本身），然后点 `Commit changes`。
5. 进入仓库的 `Settings` → `Pages`。
6. `Build and deployment` 的 `Source` 选择 `Deploy from a branch`。
7. 分支选择 `main`，目录选择 `/ (root)`，点 `Save`。
8. 等 1～2 分钟，页面会显示固定地址，通常是：

   `https://你的用户名.github.io/jlpt-n1-q4/`

9. 用手机打开这个地址，Safari 点分享 →「添加到主屏幕」。第一次联网加载后即可离线使用。

## 方法二：命令行上传

先在 GitHub 建好空仓库，然后把下面的 `你的用户名` 和 `仓库名` 换成实际值：

```sh
cd "/Users/chenxiaoshi/Desktop/工具开发/问题四开发/N2/01_线上版本/GitHub同步版"
git init
git add .
git commit -m "Add JLPT N2 question 4 study app"
git branch -M main
git remote add origin https://github.com/你的用户名/仓库名.git
git push -u origin main
```

上传后再按方法一的第 5～8 步开启 GitHub Pages。

## 两个注意点

- 免费 GitHub Pages 通常要求仓库是公开的。公开后，别人可以打开网页并保存 HTML；如果你准备售卖，单靠 GitHub Pages 不能防止内容被复制，需要另外做登录或付费墙。
- 以后更新题目后，把 `sw.js` 里的 `CACHE` 名称改成新版本（例如 `jlpt-n2-q4-v2`），否则已经安装过网页的用户可能继续看到旧缓存。
