# 空转 Wiki（部署说明）

空间转录组文献库，纯静态页面，不需要后端。

## 文件
- `index.html` 页面本体
- `data.js` 文献数据（由 build_data.py 从 Excel + extras.json 生成）
- `changelog.js` 更新日志
- `.nojekyll` 占位，告诉 GitHub Pages 不要用 Jekyll 处理

三个文件必须放在同一层目录。

## 用网页界面上传（最省事）
1. 打开 GitHub，右上角 New repository
2. 仓库名随意，比如 `st-wiki`，选 Public，不要勾选初始化 README，点 Create
3. 进入仓库，点 Add file → Upload files，把本文件夹里的 4 个文件（含 `.nojekyll`）拖进去，Commit changes
4. 仓库页 → Settings → 左侧 Pages → Source 选 `Deploy from a branch`，Branch 选 `main`、目录选 `/ (root)`，Save
5. 等 1 到 2 分钟，Pages 页面顶部会出现网址，形如 `https://用户名.github.io/st-wiki/`
6. 以后更新：重新上传改过的 `data.js` 和 `changelog.js`（`index.html` 变动时才需要传），提交后自动生效

## 用命令行（可选）
```bash
git init
git add .
git commit -m "init"
git branch -M main
git remote add origin https://github.com/用户名/st-wiki.git
git push -u origin main
```

## 注意
- 仓库必须是 Public，免费账号的 Pages 才对所有人可见
- 上传时注意 `.nojekyll` 是隐藏文件，有些系统的文件选择框看不到，可以先在资源管理器里打开「显示隐藏文件」
- 数据更新后如果页面没变，强制刷新一次（Ctrl+F5）
