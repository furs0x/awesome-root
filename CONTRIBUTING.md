# 贡献指南

向本目录新增或更正一条**临时 Root** 记录时，按本文操作。英文摘要：add a device entry only with a public source URL, model, Android version, last-verified date, and risk notes. Do not upload binaries or write exploit steps.

提交即表示你同意 [README.md](README.md) 中的免责声明，并且该记录描述的是公开资料，不是你私有的未公开利用。

## 开始之前

- 只索引你有权讨论的公开信息。不要粘贴漏洞利用、PoC、未公开攻击步骤、shell 命令序列或二进制。
- 只描述你拥有或已被授权研究的设备类别上的**公开方案**。不要征集针对特定他人设备的方法。
- 没有可打开的来源页面时，不要新建“已核实”条目。可以留在讨论里询问，不要用猜测填表。
- 不要编造工具名、GitHub 地址、CVE 编号、版本号或文件哈希。不确定就写 `TBD`。

## 必填字段

把 [docs/template.md](docs/template.md) 贴进对应品牌的 `devices/<brand>/README.md`，替换占位小节或追加在文末。下列字段缺一不可；除“类型”外，未知内容写 `TBD`，不要省略该行。

| 字段 | English | 要求 |
| --- | --- | --- |
| 品牌 | Brand | 与目录一致：Samsung、Xiaomi、Huawei、OPPO、vivo、OnePlus、Google，或其他品牌的实际名称 |
| 机型 | Model | 零售名称加地区型号（如有）。不要写“全系” |
| 代号 | Codename | 来源页面写明的设备代号。页面没有则 `TBD` |
| Android版本 | Android version | 来源声称适用的版本或安全补丁级别。不要把你自己的系统版本当成方案的适用范围，除非来源如此 |
| 方案名称 | Project name | 来源页面使用的项目或工具名称，并注明你看到的版本。页面没有稳定名称则 `TBD`，不要起新名字 |
| 类型 | Type | 固定为 `临时root`。常驻方案不要改这个字段来混入 |
| 来源链接 | Source URL | 至少一个 `https://` 页面，审阅者无需登录即可打开 |
| 最后核实日期 | Last verified | 你打开并核对来源页的日期，格式 `YYYY-MM-DD` |
| 注意事项 | Risk notes | 变砖、数据丢失、保修、闭源安装包、重启后是否失效。未知写“未知”，不要写“安全” |
| 状态 | Status | 新提交使用 `待核实`。见下文 |

来源链接的要求：

- 主链接是项目页、官方文档、上游 Release 说明或公开社区帖，页面本身要能看出机型和版本。
- 可以在同一字段补充上游 Release 里的外部安装包 URL，并写明版本号。不要只贴网盘、短链或直链 APK。
- 链接失效时不要换成另一个来路不明的镜像。把状态改为 `已失效`，在注意事项保留原 URL 和失效日期。

## 状态

| 状态 | 何时使用 |
| --- | --- |
| `TEMPLATE / 待核实` | 仅用于仓库里的空模板。提交真实记录时不要保留这个状态 |
| `待核实` | 你填好了必填字段，但还没有第二个人复核 |
| `已核实` | 复核者在该日期打开来源页，确认字段与页面一致。不表示安全 |
| `已失效` | 来源撤回、页面消失，或页面写明方案已不再工作 |
| `有争议` | 公开讨论对安全性、是否为恶意软件、或授权范围存在分歧。写清分歧和出处 |

维护者可以把 `待核实` 改为 `已核实`，但不会在没有打开来源页的情况下改状态。

## 放在哪个目录

| 品牌 | 目录 |
| --- | --- |
| Samsung / 三星 | `devices/samsung/README.md` |
| Xiaomi、Redmi、POCO | `devices/xiaomi/README.md` |
| Huawei / 华为 | `devices/huawei/README.md` |
| OPPO | `devices/oppo/README.md` |
| vivo、iQOO | `devices/vivo/README.md` |
| OnePlus / 一加 | `devices/oneplus/README.md` |
| Google Pixel | `devices/google/README.md` |
| 以上之外 | `devices/other/README.md` |

荣耀（Honor）、realme、索尼、摩托罗拉、Nothing、传音（Tecno / Infinix / itel）等先放在 `devices/other/`，品牌字段写实际品牌。不要因为芯片平台相同就并入 OPPO、vivo 或小米。

同一品牌页过长之后，可以把单机型拆到 `devices/<brand>/<model-slug>.md`（小写、数字和连字符），并在品牌 `README.md` 里链接到该文件。拆出去的文件仍使用模板中的字段表。在条目还只有两三条时，直接写在品牌 `README.md` 即可。

## 不要提交的内容

- `*.apk`、`*.apks`、`*.xapk`、`*.zip` 以及其他二进制安装包或本地解包结果
- 利用代码、补丁形式的 PoC、可直接执行的攻击步骤
- 个人身份信息、设备序列号、账号或任何凭据
- 只存在于私聊、付费群或无法公开复核的渠道中的“方案”
- 对空模板的无来源填充（把 `TBD` 换成听起来真实的工具名或链接）

安装包请留在上游 Release 或来源页面指向的外部地址。本仓库用链接索引它们，不保存文件本体。`.gitignore` 会挡住常见二进制扩展名；请不要用 `-f` 强行加入。

## Pull Request

1. 一个 PR 专注一类修改：新增若干条记录，或修正已有记录的链接/状态。不要把无关品牌的大段排版和实质内容改在一起，除非只是统一模板措辞。
2. PR 说明里列出你改了哪些机型、来源 URL，以及你核对的日期。
3. 自查工作区没有二进制：`git status` 里不应出现 `.apk` 或 `.zip`。
4. 若你只是更正自己无法复核的传闻，请改成 `有争议` 或恢复 `TBD`，不要删除别人附上的来源 URL；在注意事项追加一行说明。

审阅时维护者会打开来源链接，并拒绝无法复核、越界描述利用步骤、或携带二进制的变更。
