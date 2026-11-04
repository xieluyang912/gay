# Gay 鉴定器

一个纯前端的小玩具网页：输入名字，看 2 秒进度条，然后给出（并不科学的）鉴定结果。

- 除了你指定的名字，其他任何人都会得到「是 Gay」。
- 单个 `index.html`，零依赖，可直接放 GitHub Pages。

## 修改「不是 Gay」的名单

打开 `index.html`，找到最上面这段：

```js
const EXEMPT_NAMES = [
  // '张三',
  // '李四',
];
```

把要豁免的名字填进去即可，例如：

```js
const EXEMPT_NAMES = [
  '张三',
  '李四',
];
```

匹配时会去掉首尾空格、忽略英文大小写，必须完整同名。

想改进度条时长，就改下面的 `DURATION`（单位毫秒，默认 2000）。

## 部署到 GitHub Pages

1. 在 GitHub 新建一个仓库，例如 `gay-detector`。
2. 把本目录的 `index.html` 上传到仓库根目录（网页端 “Add file → Upload files” 即可）。
3. 打开仓库的 **Settings → Pages**。
4. **Source** 选 `Deploy from a branch`，分支选 `main`，目录选 `/ (root)`，点 **Save**。
5. 等 1 分钟左右，访问：

   ```
   https://你的用户名.github.io/gay-detector/
   ```

以后每次改完 `index.html` 提交，Pages 会自动重新发布。

## 本地预览

```bash
python3 -m http.server 8000
```

然后打开 `http://localhost:8000/`。

## 说明

所有判断都在浏览器本地完成，不会上传任何名字。结果纯属娱乐，没有任何科学依据。
