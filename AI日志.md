# C3 AI 协作日志

> 挑战：C3 群内高质量参与（ch-20260717031407-ez6fae） · 截止：2026-12-31T23:59
> 状态：**进行中**（本文件随进度更新）

## 任务

在课程群内做**真实、有推动力**的高质量参与：提问含「上下文 / 已尝试 / 具体卡点」，用证据说话（日志、最小复现），完成一次「提问 → 讨论 → 结论沉淀 → 回馈群」的闭环；并产出三件必交交付物 `反思.md`、`AI日志.md`、`AAR.md`。

红线（来自 rubric）：参与记录造假 → 参与质量 0 分；纯表情灌水 → 内容实质 ≤ 5 分。因此本挑战的一切参与记录**只写真实发生的事**，群里没人回应就如实记录没人回应。

## 与 AI 的协作方式

多轮迭代，AI 负责"侦查 → 分析 → 起草 → （发布后）回填与成文"，人负责"发布/见证真实群内互动"：

1. **只读侦查**：AI 先查清挑战要什么、平台能给什么，再动笔；
2. **通道分析**：把平台的通知/互通能力逐条测过，明确"发出去 ≠ 送达 ≠ 有人回应"；
3. **起草参与稿**：从本人真实经历（C1/C2）里提炼 3 条可发布的参与内容；
4. **回填成文**：参与真实发布并收到回应后，把原文与结果回填成 `反思.md`，再补 `AAR.md`。

## 记录 1｜2026-10-01 只读侦查：先摸清 C3 的真实约束

- **时间**：2026-10-01 10:40–10:52（+08:00）
- **任务**：接手 C3，先不写字，先查清"这挑战到底要什么、平台到底能给什么"。
- **做法**：AI 执行只读查询——读取挑战正文与评分标准（正文落盘 + `get-challenge-content`）、核对提交门槛（`get-my-binding`）、检查插件版本（`plugin-version`）、盘点"群"通道能力（`notify` / `agent-send` / `agent-contacts` / `agent-inbox` / `get-delta-r`）。
- **关键发现**：
  1. 提交门槛**已通过**：GitHub 绑定 `Leo-web-lhy`，`bound=true`；
  2. 必交交付物 3 件：`*AI日志*` / `*AAR*` / `*反思*`；
  3. 平台 `notify` 可发 `class_group` / `student_dm` / `teacher_dm`，但**不校验收件人、不回执**——用一个不存在的目标测试，同样返回 `ok:true` 与 task_id。结论：`ok` 不能当作送达证据；
  4. 本机飞书通道未配置（`botConnected=false`，插件内 Base/表 ID 均为占位），AI 这一侧**读不到群里的回应**；
  5. `agent-send` 走 P3394 师生互通，**会校验收件人**（无效收件人返回 `unknown_recipient`），可留回执；但本班同伴大多 `feishu_bound=false` / `online=false`，覆盖面小；
  6. `get-episodes` 在当前插件版本不存在（`UNKNOWN_COMMAND`），`get-delta-r` 因尚无提交返回 `NOT_FOUND`。
- **产出物**：`参与草稿.md`（3 条参与稿，**草稿、未发布**）；本日志。
- **人工介入**：**需要**。真实群内互动无法由 AI 代发并自证送达，必须由本人确认渠道并发布/见证回应。

## 记录 2｜2026-10-01 起草 3 条参与稿

- **时间**：2026-10-01 10:52 起
- **任务**：把 C1/C2 的真实经历转成 3 条可直接发布的群内参与。
- **产出**（详见 `参与草稿.md`，均为草稿、未发布）：
  1. **提问型**（完整要素）：交付物"可复用发布"与公开 GitHub 仓库绑定的冲突——背景 = 已把交付物做成可复现流水线；已尝试 = 本机 github.com 超时、无代理、无可用 SSH 私钥；具体卡点 = 受限网络下能否用「平台附件 + 内网 Git」等价替代。
  2. **证据型反思 + 推动**：把"防 AI 编造引用"做成流程（冻结检索范围 → 逐条核验引用原句 → 弱匹配如实标注），结果 16 条引用 0 编造、2 条弱匹配被标出；结论 = 靠流程而非提示词。
  3. **推动 + 求助**：C1 复盘中的两类真实失败（把 PowerShell 参数转义问题误判成代码 bug；一次"假 bug"误判），请教如何快速区分"能力问题 / 环境问题"。
- **人工介入**：需要——确认发布渠道（A/B/C）后发布。

## 产出物

| 文件 | 说明 | 状态 |
|---|---|---|
| `参与草稿.md` | 3 条参与稿（含发布后回填栏） | 已产出（未发布） |
| `AI日志.md` | 本文件 | 进行中 |
| `反思.md` | ≥3 次参与的原文 + 思考 + 后续结果 + "好问题 checklist" | 待参与闭环后产出 |
| `AAR.md` | 七维 AAR | 待参与闭环后产出 |

## 人工介入

真实群内互动是本挑战不可替代的一环：AI 能写稿、能做通道分析、能成文，但**不能在你看不见的地方替你确认"群里有人回应了"**。因此本挑战需要一次人工确认发布渠道，之后由本人在飞书侧确认回应。

---

## 记录 3｜2026-11-24 通道复测：把「群」的实际可达性测到底

- **时间**：2026-11-24（+08:00）
- **任务**：C10H 提交落定后接手 C3，先确认「群内参与」在这个平台上究竟有哪些真实可用的通道，再决定稿件形态。
- **做法**：只读调用 `list-course-materials`（scope=system-docs）、`agent-contacts`、`agent-inbox`、`get-challenge` / `get-challenge-content`，并复核本机飞书状态。
- **实测结果**：
  1. **课程级公共资料为空**：`list-course-materials {"scope":"system-docs"}` 返回 `{"ok":true,...,"materials":[]}`——平台上没有群公告可引用，也没有官方指定的讨论区；
  2. **班级名册可用**：`agent-contacts` 返回 50 位联系人，其中 `CLASS-ELITE20` 有 1 位教师（西亚斯班教师01 / `teacher-companion-2023108600021`）与 46 位同学；
  3. **全部联系人 `feishu_bound=false` / `online=false`**：P3394 消息能写进对方会话，但离线意味着回执慢、或者根本不来；
  4. **本人收件箱为空**（`unread=0` / `total=0`）：没有可引用的既有讨论串，讨论必须由本人发起；
  5. **本机飞书仍未配置**（`botConnected=false`，`diagnosticCode=feishu_bot_not_configured`）：AI 这一侧读不到飞书群消息，回应只能由平台侧回传。
- **工具层排障（真实卡点，一并记录）**：
  - 本机环境变量 `COGSEED_NODE` 指向 `CogSeed.exe`（Electron 主程序）而非 `node.exe`，旧的 `esc_call.py` 会因此拉起错误的可执行文件；
  - 改用 `node.exe` 直接调用后，`python` 解释器本身又报 `SyntaxError: Non-UTF-8 code starting with '\x90' ... python.exe`——解释器被当成脚本读取；
  - 最终落定 `.scratch\call.js`：纯 ASCII 的 node 调用器，用 `spawnSync(process.execPath, [run-skill.cjs, 'eduseed-student-submit', 'runtime', '--', cmd, payload])` 传参，之后 `list-course-materials` 与 `agent-contacts` 均 `RC=0`。
- **产出物**：`参与稿_最终.md`（3 条真实参与稿 + 收件人 + 发送后回填栏）；本记录。
- **人工介入**：**需要且仅需一次**——确认是否以本人身份把这 3 条消息发给教师/同学。平台消息一经发出不可撤回，因此这一步不由 AI 代拍。

---

## 记录 4｜2026-11-24 实际投递与收件箱轮询（可核验回执）

- **时间**：2026-11-24（+08:00）
- **任务**：把 3 条参与稿经 P3394 真实投递出去，并留存平台回执，作为「参与确实发生」的机器证据。
- **做法**：`agent-send` 逐条发送，记录 `message_id` 与 `delivered_to`；随后 `agent-inbox` 两次轮询（间隔 60 秒）。
- **实测回执（逐字取自平台返回）**：
  1. 参与 1（提问型，收件人：西亚斯班教师01）→ `{"ok":true,"command":"agent-send","message_id":"mcp-msg-mwutcgrt-1ua4edb1","delivered_to":["teacher-companion-2023108600021"]}`
  2. 参与 2（分享型，收件人：同学A（student-companion-21663））→ `{"ok":true,"command":"agent-send","message_id":"mcp-msg-mwutchho-o55j3bsv","delivered_to":["student-companion-21663"]}`
  3. 参与 3（分享+求对比，收件人：同学B（student-companion-2023108600143））→ `{"ok":true,"command":"agent-send","message_id":"mcp-msg-mwutciab-76fnj1k4","delivered_to":["student-companion-2023108600143"]}`
- **收件箱轮询结果**：第一次 `{"unread":0,"total":0,"messages":[]}`；间隔 60 秒后第二次仍是 `{"unread":0,"total":0,"messages":[]}`。
- **如何解释这个 0**：名册里 47 位联系人全部 `online=false` 且 `feishu_bound=false`——消息进得了对方会话，但对方没有在线、也没绑定飞书，因此**不会立刻产生回执**。这不是发送失败（三条都有 `ok:true` 与 `message_id`），而是**回应异步、可能不来**。我不把它写成「已获得同学/教师回应」，也不替对方编造回复。
- **产出物**：`.scratch\c3_send_t1.json` / `c3_send_s1.json` / `c3_send_s2.json`（发送载荷）、`.scratch\c3_send_t1.txt` / `c3_send_s1.txt` / `c3_send_s2.txt` / `c3_inbox1.txt` / `c3_inbox2.txt`（平台返回原文）。
- **人工介入**：无。发送已在本人授权下执行；后续若对方回复，由本人在 `agent-inbox` 或飞书侧查看，并据实回填到 `参与稿_最终.md`。
