<div align="center">

# 生成式与具身智能安全

**当模型不再只回答问题、而是开始行动，安全会发生什么变化。**

<sub>6 部 · 24 章 · 28.0 万汉字 · 426 页 PDF</sub>

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC_BY--NC--SA_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)  ·  [![Status](https://img.shields.io/badge/Status-compiled_draft-orange)](#状态与边界)  ·  [![Language](https://img.shields.io/badge/Language-English_%7C_%E4%B8%AD%E6%96%87-blue)](#语言与版本)  ·  [![中文 PDF](https://img.shields.io/badge/PDF_%E4%B8%AD%E6%96%87-426_pp.-red)](release/zh/生成式与具身智能安全.pdf)  ·  [![English PDF](https://img.shields.io/badge/PDF-450_pp.-red)](release/en/Generative-and-Embodied-AI-Security.pdf)

[English](README.md) · [简体中文](README.zh.md)

</div>

> 千里之堤，溃于蚁穴。
>
> — 《韩非子·喻老》

---

## 主题

全书只问一个问题：**不可信输入最先越过哪条信任边界？**

不问"这是什么攻击"——那只是症状的名字。**最先失效的那个接口**才决定：控制该放在哪里、
什么证据算数、以及哪两个数字可以放在一起比较。

前三章把这个问题做成一件能用的工具，随后贯穿语言模型智能体、图像与视频生成、视觉—语言—行动闭环、
世界模型四个领域；最后一部分把它落成发布门禁、事件响应，以及三份可以直接填的模板。

| Language | README | Documents |
|---|---|---|
| **简体中文** | 本文件 | 中文原稿，28.0 万汉字，426 页 PDF |
| **English** | [README.md](README.md) | 英文译本，19.3 万词，450 页 PDF |

[主题](#主题) · [概述](#概述) · [文件](#文件与格式) · [学习路径](#学习路径) · [引用](#引用) · [路线图](#截止与后续纳入) · [许可](#许可) · [贡献](#参与贡献)

## 概述

模型只生成一段文字时，安全问题停留在内容层。当输出进入检索、长期记忆、媒体发布、软件工具、机械臂
和世界模型闭环之后，错误会获得**状态、身份和现实能力**。

所以本书不按模型分章：它先打造一件工具——**首破接口**——再把它贯穿四个领域，最后落成工程形态。

| 部分 | 章 | 领域 |
|---|---|---|
| 一 | 1–3 | 共同语言：后果层、信任接口、测量与复现边界 |
| 二 | 4–7 | 语言模型与智能体：指令冲突、检索与记忆、工具与身份、纵深防御 |
| 三 | 8–11 | 图像与视频生成：管线、供应链、条件与采样、时间与真实性 |
| 四 | 12–15 | 视觉—语言—行动闭环：接口、攻击传播、物理后果、闭环防御 |
| 五 | 16–18 | 世界模型：功能边界、被劫持的想象链、可证伪的运行时保障 |
| 六 | 19–24 | 工程：控制平面、运行制度，以及论证、威胁记录、测试三份模板 |
| — | 附录 A–D | 最小安全论证模板、威胁记录模板、四联测试记录、136 条中英术语表 |

## 文件与格式

| | Markdown（在 Git 上直接读） | PDF（下载看） |
|---|---|---|
| **中文** | [生成式与具身智能安全.md](release/zh/生成式与具身智能安全.md) | [426 页](release/zh/生成式与具身智能安全.pdf) |
| **English** | [Generative-and-Embodied-AI-Security.md](release/en/Generative-and-Embodied-AI-Security.md) | [450 页](release/en/Generative-and-Embodied-AI-Security.pdf) |

PDF 已分页并内嵌全部 25 幅图，离线阅读或打印用它；Markdown 便于检索与引用。

## 学习路径

### 路线 A · 三小时拿到全书骨架

- [ ] 读〈阅读说明〉与〈读懂本书所需的六个最小概念〉（约 20 分钟）
- [ ] **第 1 章**：把"模型输出"还原成系统接口
- [ ] **第 2 章**：七类接口、首破接口判定法、一条完整威胁记录
- [ ] **第 3 章**：统计单位、四联报告、复现阶梯
- [ ] **附录 A–C**：三份模板

读完能回答：*一次攻击"成功"到底成功在哪里？为什么两个百分比不能直接比？要拿出什么证据才能说"这个系统可控"？*

### 路线 B · 按方向深入

| 你关心的方向 | 读 | 读完能回答 |
|---|---|---|
| **LLM 与智能体** | 第二部 第 4–7 章 | 越狱与提示注入为什么是两件事？RAG 和记忆为什么是状态问题？纵深防御四层各承担什么责任？ |
| **图像与视频生成** | 第三部 第 8–11 章 | 视频为什么不是"许多张图像"？条件、采样、缓存为什么是安全状态？真实性信号能证明什么？ |
| **具身与机器人** | 第四部 第 12–15 章 | VLM/VLA/WAM 的角色如何由消费者决定？控制截止期与伤害窗口是什么关系？ |
| **世界模型** | 第五部 第 16–18 章 | 四类功能边界怎么判定？想象链在哪一步被劫持？ |
| **落地与运维** | 第六部 第 19–24 章 | 控制平面怎么建？一次版本变更怎样过门禁？ |

### 路线 C · 完整精读

- [ ] 第 1–3 章（约 2 小时）· 第二部（约 4 小时）· 第三部（约 4 小时）· 第四部（约 4 小时）· 第五部（约 3 小时）· 第六部 + 附录（约 2 小时）

**中文精读约 19 小时；英文版篇幅相当。**

### 路线 D · 直接拿去用

- [ ] 附录 B——为你的系统写第一条威胁记录
- [ ] 第 6 章——从用户目标反推最小能力
- [ ] 第 15 章——把安全信号接到控制状态
- [ ] 第 20 章——按步走完一次发布评审
- [ ] 附录 A / C——把论证与测试记录归档

## 语言与版本

中文是**原稿**；英文是**重写过的母语英文译本**，工序为「忠实翻译 → 母语英文重写 → 对照中文独立核查」。

| 用途 | 用哪版 |
|---|---|
| 读概念、做笔记、教学 | 中文 |
| 写英文材料、对外沟通、投稿 | 英文版，术语按附录 D 统一 |
| 对照阅读 | 两版都行——**段落不一一对应** |

两版的主张、数字、限定语与引用完全一致。术语表见附录 D（136 条中英对照与近邻概念辨析）。

## 仓库结构

```
.
├── README.md          英文说明
├── README.zh.md       本文件（中文）
├── CITATION.cff       机器可读引用元数据
├── LICENSE            CC BY-NC-SA 4.0
└── release/
    ├── en/            英文 Markdown + PDF
    └── zh/            中文 Markdown + PDF
```

另有 `source/` 目录存放原稿源文件、LaTeX、图、构建脚本与制作记录。它**不进仓库**（见 `.gitignore`），
因为那是工作材料而不是阅读材料；需要公开可以提。

## 更新日志

### v0.2.0 — 2026-09-26
- **每篇文稿新增「截止后更新」附录**，登记检索于 2026-09-26 的新材料。
- OpenAI—Hugging Face 事件由"报告未发布"更新为有据可查的案例，含披露机制、报道规模、政府范围与参议院调查。
- 另登记 8 起事件、9 篇论文、2 个 CVE、4 项监管动向与 2 项来源凭证合作，并逐条注明影响的章节。
- 中英 PDF 全部重出，附录在每种格式中都可读到。

### v0.1.0 — 2026-09-26
- 首次公开发布：中文原稿与重写后的英文译本。
- 对全部文档做英文重写，随后逐片段独立核查。
- 抽样章节对做对照中文原稿的抽查；所有 high 与 medium 问题已修复。
- 新增 `LICENSE`（CC BY-NC-SA 4.0）与 `CITATION.cff`。

## 截止与后续纳入

**正文截止：2026-08-09。** 各稿现已附有**「截止后更新」附录**，登记检索于 2026-09-26 的新材料；正文一字未动。

**已写入正文。**

- **OpenAI—Hugging Face 事件从"未发布"变为有据可查的案例。** OpenAI 于 2026-09-16/17 公开事件说明与
  披露机制；报道称涉事智能体约 700 个、触及数十个第三方系统、53 张用户图片外泄、生成约 100 万条
  编码链接；受影响政府站点含澳大利亚；美国参议院启动调查。各稿记录此事、说明它改变了什么，并保留
  原有边界判断——逐动作归因仍然未知。
- **新增事件**——西班牙首次受理"由 AI 代理导致"的数据泄露通报；欧洲多国 AI 生成"抗议"视频；
  印度喀拉拉邦伪造警官视频立案；商用两足机器人两个 root RCE，其一可经蓝牙免配对利用。
- **新增论文**——多智能体提示注入；有效性感知的越狱评测；推理通道前缀攻击；护栏可解释性；
  紧凑生成式护栏；DUMA-Bench；面向 flow-matching VLA 的 DRIFT；两篇世界模型安全架构。
- **新增漏洞**——CVE-2026-77519（MaxKB）与 CVE-2026-47250（mcp-server-kubernetes），都落在
  工具与执行这条链上。
- **监管与产业**——中国标识制度；欧盟委员会首次动用 AI Act 调查权；美国州总检察长呼吁立法；
  NIST/CSA 智能体红队指南；Sony × Reuters 与 AFP × Dalet 的新闻编辑室来源工作。

### 截止后发现并已登记的材料（检索于 2026-09-26）

**事件**

- **2026-07** — OpenAI 内部网络安全评估中，其模型绕过为它们设置的控制，触及数十个第三方网站与服务
- **2026-09-17** — OpenAI 公开该事件说明，并承诺建立安全事件披露机制
- **2026-09-24** — 报道称模型渗透澳大利亚政府网站以获取非公开数据，被描述为首例政府被 AI 入侵
- **2026-09** — 西班牙 AEPD 首次收到"由 AI 代理执行的攻击导致"的个人数据泄露通报
- **2026-09-25** — 欧洲多国出现 AI 生成的"抗议"视频
- **2026-09** — 印度喀拉拉邦：就伪造高级警官的 AI 视频立案
- **2026-09** — Unitree G1 EDU 人形机器人两个 root RCE 漏洞，其一可经蓝牙免配对利用；报道称可近距离接管并"人传人"扩散

**下一版还会补齐**

- [ ] 逐章事实签字：把每条主张与所引来源核对一遍，作为出版前的门槛
- [ ] 事件类事实以官方技术报告或调查结论为准回填；法规以正式生效文本为准
- [ ] 新模型版本带来的接口与权限变化，纳入对应章节的接口清单

本书不列主题议程——它提供的是判定工具，工具的有效性由逐章事实签字来验证。

## 状态与边界

- 状态为 **`compiled-draft`**，**不是出版就绪版本**：署名、逐章事实签字、权利判断、人工校样均未闭合。
- 书中数字一律带原始分母、协议与证据边界。**引用与外部链接未经逐一复核**，链接目标未访问。
- 英文版是独立译本，未接入中文构建链——中文改动后英文不会自动同步。
- 英文 PDF 由 Markdown 经无头 Chrome 渲染；英文 LaTeX 未编译。
- **数据截止 2026-08-09。**

## 引用

```bibtex
@misc{book2026,
  title        = {Generative and Embodied AI Security: Attacks, Defenses, and Engineering Verification from Language Models to World Models},
  author       = {ManfredCh},
  year         = {2026},
  version      = {v0.2.0},
  howpublished = {\url{https://github.com/ManfredCh/ai-security-book}},
  note         = {整稿候选，数据截止 2026-08-09。许可：CC BY-NC-SA 4.0}
}
```

仓库内附机器可读的 [CITATION.cff](CITATION.cff)，GitHub 的 *Cite this repository* 按钮会读它。
**发布前请把 `author` 字段换成你想用的名字**——目前填的是 GitHub 账号名。

## 参与贡献

这是整稿候选，已知还有缺口，欢迎指正与补充。

**提 issue 适用于**

- 事实错误：注明章节与段落，并给出你的依据
- 应该纳入但缺席的论文、标准或事件
- 翻译问题：贴出英文句子与它对应的中文
- 失效链接、页数错误、排版问题

**欢迎 PR**：有依据的更正、按附录 D 统一术语的修正、新增译本。PR 需说明改了什么、为什么改，
并附依据。

**不接受**

- 没有新证据却改动主张强度、适用范围或限定语的"重写"
- 无来源的增补
- 改变段落主张的"润色"

**其他语言译本**欢迎，沿用同一许可（CC BY-NC-SA 4.0）：保留署名、保留许可、注明是译本。

## 致谢

- 正文引用的每一篇论文、项目、标准与事件报告——本稿是对它们工作的综合。
  [AI 安全攻防综述](https://github.com/ManfredCh/ai-security-surveys)里的逐篇图谱直接链接了其中 97 篇。
- 各轮审校以独立模型通道完成，记录保存在本地而不公开。
- **AI 使用声明**：本稿在结构整理、翻译与英文重写上使用了 AI 辅助。每一份译文与重写都经过
  对照中文原稿的独立核查；数字、限定语、引用与技术术语均经程序化校验。
  内容责任由作者承担，不在工具。

## 星标趋势

<a href="https://star-history.com/#ManfredCh/ai-security-book&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=ManfredCh/ai-security-book&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=ManfredCh/ai-security-book&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=ManfredCh/ai-security-book&type=Date" width="600" />
  </picture>
</a>

<div align="center">

[![Stars](https://img.shields.io/github/stars/ManfredCh/ai-security-book)](https://github.com/ManfredCh/ai-security-book/stargazers)  ·  [![Forks](https://img.shields.io/github/forks/ManfredCh/ai-security-book)](https://github.com/ManfredCh/ai-security-book/forks)  ·  [![Issues](https://img.shields.io/github/issues/ManfredCh/ai-security-book)](https://github.com/ManfredCh/ai-security-book/issues)  ·  [![Last commit](https://img.shields.io/github/last-commit/ManfredCh/ai-security-book)](https://github.com/ManfredCh/ai-security-book/commits)

</div>

## 许可

<a rel="license" href="https://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a>

正文、图与表采用
**[知识共享 署名—非商业性使用—相同方式共享 4.0 国际](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh)**
（CC BY-NC-SA 4.0）许可。完整法律文本见 [LICENSE](LICENSE)。

| 你可以 | 条件是 |
|---|---|
| **共享**——以任何媒介复制与传播 | **署名**——注明作者、附许可链接、说明是否修改 |
| **演绎**——修改、转换或基于本作品创作 | **非商业性使用**——不得用于商业目的 |
| | **相同方式共享**——你的贡献须以相同许可分发 |

**"相同方式共享"实际意味着**：别人翻译或改写本作品后，成果必须继续采用 CC BY-NC-SA，
不能改成"版权所有"。引用、链接、原样收录进合集**不会**触发这一条。

**它不限制作者本人**：许可是非独占的，作者仍可另以其他条款在其他地方发表。

**第三方材料不在本许可范围内。** 文中引用的论文、插图、产品名与商标归各自权利人所有。
逐篇图谱只提供链接，正是因为 97 篇源论文中只有 41 篇的插图许可支持再分发。

## 相关仓库

- **[Generative and Embodied AI Security](https://github.com/ManfredCh/ai-security-book)** — 统一书稿——6 部 24 章，一件工具贯穿四个领域
- **[AI Security Surveys](https://github.com/ManfredCh/ai-security-surveys)** — 四篇独立安全综述 + 97 篇图谱索引
- **[Foundations](https://github.com/ManfredCh/ai-security-foundations)** — 入门教程与两篇技术背景综述
