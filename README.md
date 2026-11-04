# awesome-root

按品牌和机型整理**公开资料**里的 Android **临时 Root** 方案：记录来源链接、适用版本和风险说明，方便在自己的设备上核对。

这是文档目录，不是软件分发站，也不是漏洞利用集合。

**English.** A documentation catalog of publicly described temporary Android root methods (APK-based or one-click), indexed by brand and model. Entries point at external source pages and notes. This repository does not host exploit code, payloads, or installer binaries, and it does not claim any method is safe or still works.

当前仓库里的机型条都是空模板（`TEMPLATE / 待核实`）。在贡献者按 [CONTRIBUTING.md](CONTRIBUTING.md) 填入可打开的公开来源之前，它们不是可用方案。

## 免责声明

先读完本节再使用任何条目。

1. **只用于你拥有，或已获得明确授权管理的设备。** 未经授权访问、控制或修改他人设备违法。
2. **临时 Root 可能变砖、丢失数据、触发保修熔断（例如 Knox 或厂商等效机制）、使保修失效，或导致之后无法正常接收安全更新。** 操作前自行备份，并接受设备可能无法恢复。
3. **请自行研究。** 链接由贡献者提交。本仓库不审计第三方安装包或网站，也不为其安全性背书。
4. **本仓库不托管利用代码，不保证安全，也不保证某一方案仍然有效。** 不要在 Issue 或 Pull Request 里粘贴漏洞利用、PoC、未公开的攻击步骤或二进制。用公开网页链接说明来源即可。
5. **优先引用官方或社区的原始页面，不要上传安装包。** 二进制留在上游 Release 或其他外部渠道。本仓库拒绝提交 `*.apk`、`*.zip` 等二进制文件。
6. 字段为 `TBD` 的模板**没有核实过的信息**。不要依据空模板对设备做任何操作。

## 收录范围

收录对象是已经出现在公开网页上的临时 Root：通常由 APK、一键工具或一次授权完成，重启或会话结束后权限一般会消失。一条合格记录至少要能回答：哪一个具体机型、哪个 Android 版本、方案叫什么、来源页面在哪里、哪一天有人打开该页面核对过、已知风险是什么。

以下内容不收入，也不要在条目里展开步骤：

- 漏洞利用代码、复现步骤、未公开的攻击细节
- APK、ZIP 和其他二进制安装包（含哈希冒充“已验证”）
- 编造的工具名、仓库地址、CVE 编号或校验值
- 需要解锁引导加载程序后长期改写 boot / 系统分区的常驻方案，除非来源页面明确把它描述为临时方案
- 针对不属于你的设备的用途

没有核实过的公开项目时，保持模板。空字段比一条看上去完整、实际无法复核的记录更有用。

## 目录

| 路径 | 内容 |
| --- | --- |
| [README.md](README.md) | 总索引、免责声明、贡献入口 |
| [CONTRIBUTING.md](CONTRIBUTING.md) | 新增机型记录的要求 |
| [LICENSE](LICENSE) | MIT |
| [docs/template.md](docs/template.md) | 单机型条目模板 |
| [devices/](devices/) | 按品牌分目录 |

### 品牌索引

| 品牌 | 索引 |
| --- | --- |
| Samsung / 三星 | [devices/samsung/README.md](devices/samsung/README.md) |
| Xiaomi / 小米（含 Redmi、POCO） | [devices/xiaomi/README.md](devices/xiaomi/README.md) |
| Huawei / 华为 | [devices/huawei/README.md](devices/huawei/README.md) |
| OPPO | [devices/oppo/README.md](devices/oppo/README.md) |
| vivo（含 iQOO） | [devices/vivo/README.md](devices/vivo/README.md) |
| OnePlus / 一加 | [devices/oneplus/README.md](devices/oneplus/README.md) |
| Google Pixel | [devices/google/README.md](devices/google/README.md) |
| 其他品牌 | [devices/other/README.md](devices/other/README.md) |

上表指向的页面目前只有占位条目，字段为 `TBD`。这不是“已知可 Root 机型”清单。

## 字段与状态

单条记录的字段见 [docs/template.md](docs/template.md)：品牌、机型、代号、Android版本、方案名称、类型、来源链接、最后核实日期、注意事项、状态。类型固定为 `临时root`。

| 状态 | 含义 |
| --- | --- |
| `TEMPLATE / 待核实` | 仓库自带的空模板，没有方案 |
| `待核实` | 已填写来源，还没有其他人复核 |
| `已核实` | 在“最后核实日期”打开过来源页，字段与该页一致。不表示方案安全或仍然可用 |
| `已失效` | 公开资料表明该方案已不可用 |
| `有争议` | 安全性、合法性或来源可信度存在公开争议。保留链接，并在注意事项写明争议点 |

## 二进制文件

[`.gitignore`](.gitignore) 忽略 `*.apk`、`*.zip` 以及常见安装包和编辑器垃圾文件。需要提供安装包时，使用上游 Release 或来源页面给出的外部链接，把 URL 写入“来源链接”。不要把二进制加入 Git 历史；一旦进入历史，仅靠后续删除工作区文件并不能把它从克隆中去掉。

## 如何贡献

1. 阅读 [CONTRIBUTING.md](CONTRIBUTING.md) 和上面的免责声明。
2. 从 [docs/template.md](docs/template.md) 复制一节，填入你打开核对过的公开来源和机型信息。
3. 把该节加入对应的 `devices/<brand>/README.md`。一个方案覆盖多个机型时分开写；来源没有点名的型号不要推断为“全系通用”。
4. 提交 Pull Request。没有来源链接、或含有本仓库二进制的提交不会被接受。

无法确认的字段保持 `TBD`，并在注意事项里写明哪一部分没有核实。

## 许可证

文档以 [MIT License](LICENSE) 授权。第三方页面、商标和工具名称归各自权利人。收录一个链接不表示隶属、合作或安全背书。
