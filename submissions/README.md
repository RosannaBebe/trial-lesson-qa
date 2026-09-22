# 评分提交（看板 / 导出数据源）

每次点「提交评分」都会**新建一个文件**，不会覆盖、不会合并。

## 目录

- 仓库：https://github.com/RosannaBebe/trial-lesson-qa
- 文件夹：[`submissions/`](https://github.com/RosannaBebe/trial-lesson-qa/tree/main/submissions)
- 原始文件：`https://raw.githubusercontent.com/RosannaBebe/trial-lesson-qa/main/submissions/<文件名>.json`
- 列出全部提交：`GET https://api.github.com/repos/RosannaBebe/trial-lesson-qa/contents/submissions`

## 文件名

`{UTC时间}-{Level}-{版本}-{随机}.json`

例：`20260922T014615Z-L3-V2-k7f2a9.json`

打分人姓名写在 JSON 里的 `rater`，不写进文件名。

## 字段（schema = `trial-qa-submission-v1`）

| 字段 | 用途 |
| --- | --- |
| `id` | 这次提交的唯一 ID |
| `submittedAt` | ISO 时间 |
| `rater` | 打分人姓名 |
| `level` / `version` | 如 L3 / V2 |
| `course` | 课名、`lessonId` |
| `score` / `maxScore` | 总分 |
| `globals[]` | 全局项（课堂节奏等），`result` = `pass` / `fail` / `unselected` |
| `rows[]` | 按 template 行汇总 |
| `items[]` | **扁平行**，适合看板和导出 CSV |

`items[].result`：

- 普通格：`pass`（达成）/ `fail`（未达成）/ `unselected`（未选）
- 环节耗时：`ok`（≤2 分钟）/ `half`（超过 2 分钟）/ `fail`（超过 5 分钟）/ `unselected`

看板按 `rater + level + version + submittedAt` 分组即可做多人对比；不要把多次提交叠进同一个文件。
