# AGENTS.md — 外链资源池

## 仓库性质

纯文档项目，无代码、无构建/测试命令。内容是"新项目上线该往哪儿投稿"的外链渠道清单：主文件 `外链资源池-YYYY-MM-DD.md`（按日期命名的快照）+ `README.md`。推送到公开仓库 the-beating-light-of-the-nail/backlink-resource-pool。

## 编辑主清单的规则（改一处必须同步四处）

新增/删除渠道时，以下计数要一起改，漏一处就数字对不上：

1. 文档头部"总览"表对应分段的行数
2. 该分段标题里的数量（如 `## F. 中文导航/作品集市（6 个）`）
3. "总计 N 个独立外链资源"一行
4. `README.md` 里的资源总数

另外：文档头"整理日期"行追加 `(YYYY-MM-DD 新增 …)` 形式的更新备注；新渠道按类型归段（GitHub awesome list → A/B/C/K，Launch 平台 → D，目录站 → E，中文导航 → F，自家仓 → G，社区/杂项 → H）；用户实测过的渠道在备注列标"已实测"。

K 段是 2026-09-09 从 [sindresorhus/awesome](https://github.com/sindresorhus/awesome) 元列表（674 个清单仓）全量筛选的产物：K1/K2 为可投渠道（带适合项目与分区），K3 为核验后排除的参考（含排除原因），渠道复活或改规则时再调整。

## Git 与网络 gotchas

- **本机没有 `gh` CLI**。建仓/查 API 用 Git Credential Manager 里的凭据：`printf "protocol=https\nhost=github.com\n\n" | GCM_INTERACTIVE=never git credential fill` 拿 token，再 curl 调 api.github.com。
- **代理端口不固定**：7897 和 7890 都出现过（Clash 端口切换过）。推送前先 `netstat -ano | grep LISTEN` 探测当前监听端口，用 `git -c http.proxy=http://127.0.0.1:<port> push`；直连偶尔也通，代理连不上时试直连。
- curl 在 Git Bash 下传中文 JSON 会坏（Windows curl 的引号解析问题），JSON 参数一律写临时文件用 `-d @file`。
- 提交身份按 git-identity 技能规则：本仓不在 alexanderdcervantes 镜像链路 → 用 the-beating-light-of-the-nail 身份。

## 内容红线

- 清单里的 star 数为 2026-09-09 实测快照，DR / 月访仍为历史快照，实投前都要重新核验。
- 台账随项目仓走：每个项目仓根目录的 `backlinks.md`（投稿前先查本项目台账防重）；文末台账表已改为项目仓路径，历史 `/root/...` JSON 台账不再维护。
- J 段（停更/失效档）为不投渠道，仅留档；渠道复活时再移回对应分段。K3 同理，是元列表核验后排除的参考，不投。
- 黑名单（26 个）是已确认排除的平台，不进任何推荐。
