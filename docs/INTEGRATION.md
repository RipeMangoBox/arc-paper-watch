# 数据维护与既有任务接入

`data/papers.json` 是唯一论文数据源。`README.md` 与 `dist/index.html` 是确定性生成结果，不要手改。阅读器内嵌样式、脚本与论文内容，可直接离线打开。

收录范围为 [腾讯 ARC 官方 academic 列表](https://arc.tencent.com/academic) 中录用年份为 2024 年及以后的论文。截止 2026-10-13 共 80 篇；首次公开日期单独记录，不能据 arXiv 年份排除官方列表中的早期预印本。复用 RPW 的数据格式、可折叠简介、徽章、阅读器、校验与发布流程。本仓库没有配置定时监控。

## 本地使用

要求 Python 3.9+；阅读器测试要求 Node 18+。所有脚本无第三方依赖。推送还需要已有登录的 GitHub CLI 与 Git。

```bash
python3 scripts/paper_watch.py validate
python3 scripts/paper_watch.py build
python3 scripts/paper_watch.py build --check
python3 -m unittest discover -s tests -v
node --test tests/reader.test.cjs
```

直接用浏览器打开 `dist/index.html`。E 全部展开，C 全部收起；优先级、研究方向和关键词可组合筛选，关键词覆盖标签与录用信息。搜索框、选择框、可编辑内容、输入法组合期间和任何修饰键组合均不触发快捷键。可关闭快捷键，所有操作均有可聚焦按钮。筛选不改变展开状态；全部展开/收起包括当前被筛选隐藏的论文。

GitHub README 使用每篇 `<details>` 折叠，支持 Tab 聚焦后 Enter / 空格切换；GitHub 不执行 README 自定义 JavaScript，E / C 在[在线阅读页](https://ripemangobox.github.io/arc-paper-watch/)中提供。标题、arXiv / Website 与 Star 徽章采用 Awesome-Video-Diffusion 的条目风格；Star 指向各论文的官方代码仓库。

[离线 ZIP](https://ripemangobox.github.io/arc-paper-watch/research-paper-watch.zip)解压后直接打开 index.html，也可在在线页右上角下载单个 HTML。正文、搜索、折叠均可离线使用；Star 徽章联网显示。不再使用 Raw HTML 作为下载入口。

当前 GitHub 授权不包含上传 Actions 工作流的权限，本仓库采用 `gh-pages` 分支作为静态 Pages 来源。先运行本地校验与测试，再执行 `python3 scripts/package_reader.py` 打包 ZIP，最后将 `dist/index.html` 和 `dist/research-paper-watch.zip` 同步到 `gh-pages` 分支根目录。ZIP 只含 index.html。`main` 保存目录数据和阅读器源码；仅推送 main 不会自动更新在线页。

## 增量数据格式

批次是一个 UTF-8 JSON 对象：`{"schema_version":1,"papers":[...]}`。空数组是合法的“本次无新增”。仅导出经过核实的公开论文资料，原始批次放在被 Git 忽略的 `incoming/`。

每篇字段如下。未知值使用 `null`，不能猜测。

| 字段 | 含义 |
| --- | --- |
| `title`, `short_name` | 论文完整标题、简短名称，单行纯文本 |
| `published` | 首次公开日期 `YYYY-MM-DD`；未知为 `null`，不能用收录日期替代 |
| `category` | 视频生成基础 / 少步蒸馏 / 交互长视频 / 流式系统 / 具身与世界模型 / 交互 Avatar / 智能体与上下文 / 多模态检索 / 评测与可靠性 / 训练与推理效率 / 多模态架构与综述 / 三维生成与重建 / 图像生成与编辑 / 视频理解与推理 / 语音与音频 / 视觉感知 / 领域应用 |
| `venue`, `venue_url` | 录用会议或期刊及年份、核验来源；未证实则明确标注待核实 |
| `priority`, `priority_reason` | P0 必读 / P1 重点 / P2 选读 / P3 暂缓，及结合研究目标的推荐理由 |
| `reading_status` | `abs-intro` 摘要与引言；`full-text` 已核对正文；`metadata-only` 待补引言，仅作占位 |
| `tags` | 最多 12 个短标签组成的数组 |
| `arxiv_id` | 如 `2412.07772`；无则 `null`，版本号会被去除 |
| `doi` | 已核实 DOI；无则 `null` |
| `paper_url` | 可公开访问的论文详情链接，优先 arXiv 或 DOI |
| `links` | `project`、`code`、`weights` 三个键；已验证官方链接或 `null` |
| `summary` | `problem`、`method`、`value`、`limitation` 四个键，合计 80–160 字符的独立中文提炼 |
| `evidence_urls` | 至少一个作者论文、官方项目或官方仓库等一手来源 URL |
| `verified_at` | 本次实际核验日期 `YYYY-MM-DD` |
| `id` | 可省略，由导入器根据标识生成 |
| `first_seen`, `last_seen`, `discovery_sources` | 批次可省略，由导入命令记录；不要填私人任务 ID |

数据示例见 `data/papers.json` 中的真实条目。脚本拒绝未知字段、文件路径、私网链接、带凭据的 URL、明显凭据字符串、HTML 和多行原始笔记。这些格式约束不能代替对公开范围和论文真实性的核验。

## ARC 阅读导入

采用 `arc-academic` 来源标记。每篇至少阅读摘要和引言，再写问题、方法、价值和局限。两篇待补条目当前只完成身份与录用核验，`reading_status` 为 `metadata-only`，不声称读过引言。所有优先级基于视频生成、实时 Avatar、世界模型、Agent 规划与记忆；不是论文质量排名。

```bash
python3 scripts/paper_watch.py import incoming/2026-10-13-arc.json --source arc-academic --date 2026-10-13 --dry-run
python3 scripts/paper_watch.py import incoming/2026-10-13-arc.json --source arc-academic --date 2026-10-13
```

去重比较所有可用身份：去版本 arXiv ID、大小写归一 DOI、规范论文 URL。arXiv DOI 与对应 arXiv ID 互通。URL 去除 fragment、常见跟踪参数和末尾斜杠，保留真正的查询参数；不因标题相似而合并。

重复执行同日批次是幂等的；不同来源命中同一论文合并来源集合。较新核验内容更新旧摘要；未知链接不删除已验证链接。冲突的论文标识会停止导入。`flock` 串行化本机并发运行，文件分别原子替换；如进程在多文件写入间意外中断，可重新执行 `build` 修复展示结果。同一仓库应使用同一个本地 checkout；多个主机同时推送仍可能产生 Git 分歧，需人工合并。

## 人工核验后的发布命令

从干净的仓库开始，直接让发布脚本完成“拉取 → 导入 → 生成 → 测试 → 提交 → 推送 → 核对远程提交”；不要先运行会修改工作树的本地导入。

```bash
# 默认只预览，不写论文文件、不联网
python3 scripts/publish.py incoming/2026-10-13-arc.json --source arc-academic --date 2026-10-13

# 仅在本批次已经过公开内容核验后执行
python3 scripts/publish.py incoming/2026-10-13-arc.json --source arc-academic --date 2026-10-13 --push
```

下述脚本仅同步 main 中的目录文件；在线发布还需按上节同步 gh-pages。发布目标固定为 `RipeMangoBox/arc-paper-watch`，要求 `main` 分支、干净工作树、已有 `RipeMangoBox` 登录。只暂存 `data/papers.json`、`README.md`、`dist/index.html`；已有未推送提交也必须只涉及这三个文件。不创建 token，不上传输入批次或其他文件，不强制推送、不改 GitHub 权限。

失败会停止并保留本地状态；若仅推送失败且工作树仍干净，可重试相同命令。权限错误、脏工作树或分歧不得通过覆盖或强制推送解决。

## 首批核验与待补阅读

2024 年 33 篇、2025 年 21 篇、2026 年 26 篇，逐项与官方 API 列表对应；不存在因主题偏好而丢弃的条目。摘要与引言已完成 78 篇。

- ViewWeaver（SIGGRAPH 2026）：官方 DOI 页面未能取得可读全文，暂定 P2。
- Chinese Title Generation for Short Videos（TPAMI 2024）：未取得期刊版引言；不以早期 CREATE 会议稿替代，暂定 P2。
- 官方列表的 SEED-Bench 条目指向 SEED-Bench-2（arXiv:2311.17092），标题与导读按实际链接版本记录。

日期、录用信息、推荐理由和可读版本的公开链接均保存在各条目中。PDF、原始摘录和中间阅读材料不上传。
