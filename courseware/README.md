# 课件图（打分人只看、维护人上传）

这里是**官方课件图**。打分人打开普通打分页就会自动加载，不能自己传图。

## 你怎么维护

1. 只用这个维护链接打开：  
   https://rosannabebe.github.io/trial-lesson-qa/?owner=1
2. 第一次点「课件设置」，粘贴有 `repo` 权限的 GitHub Token（只存在你这台电脑）。
3. 选好 Level 和版本，在每一行的「课件」格点「上传」。
4. 全部传完后，点「发布课件图」。图会写进本目录。
5. 打分人用普通链接即可：  
   https://rosannabebe.github.io/trial-lesson-qa/  
   他们只看图，没有上传按钮。

换图：再走维护链接，覆盖上传同一行，再点一次「发布课件图」。

## 文件

- 清单：`courseware/manifest.json`
- 单图：`courseware/{Level}__{old|neu}__{rowId}.jpg`  
  例如 `L3__neu__1a.jpg`（`old` = V1，`neu` = V2）
