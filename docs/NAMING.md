# 命名决策记录 · NAMING

> 本文件记录「汲古」这个名字是怎么定下来的、否掉了哪些、以及中英名如何对应。改名前请先读完。

---

## 一、最终命名

| 项 | 值 | 说明 |
|---|---|---|
| 中文名 | **汲古** | 对外口头称呼；品牌层 |
| 英文名 | **Dossier** | 与中文名同源不同义：汲古说动作，Dossier 说容器 |
| 正式全称 | 汲古 · 个人文档知识库 | 只在首次出现、文档标题、对外介绍时用 |
| GitHub 仓库 | `ShenpingDD/personal-dossier` | 全小写连字符；`personal-` 是三条硬约束的可见标记 |
| 副标（中文） | 售前与项目经理的个人文档知识库 | 一句话说清给谁、是什么 |
| PyPI 包名 | `personal-dossier` | 2026-11-25 核查未注册 |
| Python 模块 | `personal_dossier` | 与包名一致，避免与已有包重名 |
| CLI | `dossier` | 子命令：`parse` / `loc` / `eval` / `ask` |
| 域名（备用） | jigu.cc / personal-dossier.com | 均未核查，需要时再占 |

**一句话定位**：一个客户一卷，问出来每句带出处。

### 中英名怎么对应

不是翻译关系，是分工关系：

```
personal-dossier   =   personal（约束）+ dossier（英文品牌词干）
                          │                    │
                   三条硬约束            汲古的中文名
                  不出本机/单人/长跑      （汲古：从旧卷里汲水）
```

- 「汲古」说的是**动作**：你的旧方案还在，等着被汲上来。
- 「Dossier」说的是**容器**：一个客户一卷。
- 「personal-」说的是**代价与边界**：砍掉协作、权限、云同步。
- 「个人文档知识库」说的是**品类**：让搜索和第一眼归类有落点。

同一个东西四个词，各管一层，互不替代。

### 用法规范

| 场合 | 写法 |
|---|---|
| 文档标题 / 首次出现 / 对外介绍 | 汲古 · 个人文档知识库 |
| 第二次起 / 口头 / 群聊 | 汲古 |
| 英文语境 / 代码仓库 | Dossier（仓库地址 `personal-dossier`） |
| 命令 | `dossier parse report.pdf` |
| ❌ 不要写 | 「汲古知识库」（品类重复）、「Personal 汲古」（中英混写）、「个人卷宗」（旧名，已废弃） |

### 两个命名坑（已核查，2026-11-25）

- **PyPI `jigu` 已被占**：是 Terra 区块链的 Python SDK（v0.1.4，`jigu.terra.money`），且 npm 上 `jigu` 也被占。所以中文名的拼音不能当包名，包名回归 `personal-dossier`。
- **PyPI / npm `dossier` 也被占**：所以 `dossier` 只能做 CLI 命令名，不能做包名。包名与命令名分离是常见做法（如 `pillow` → `PIL`）。

---

## 二、命名结构：三层，各管一件事

名字出问题，通常是三层挤在一起。本项目的定法是：

| 层 | 回答什么 | 落在哪 | 取值 |
|---|---|---|---|
| **品类层** | 这属于什么产品 | description / topics / README 第一句 | 个人文档知识库 · Personal Document KB |
| **角色层** | 给谁用 | README 副标 | 售前解决方案经理 · 项目经理 |
| **名字层** | 我叫它什么 | repo slug / 中英名 / CLI | 汲古（Dossier）· `personal-dossier` |

**规则：名字负责被记住，品类负责被搜到。名字里塞品类，两边都丢。**

这就是为什么 slug 不用 `personal-kb`，但 description 和 topics 里「个人知识库」「Personal Knowledge Base」一个都不能少。

---

## 三、为什么是「卷宗」

1. **它是售前真实的工作单位。** 客户不会说「帮我找那份 PDF」，他说「把那个客户的资料都调出来」——检索的起点是一卷，不是文件。
2. **它自带归档与可追溯。** 卷宗有封面、有目录、有页码，和本项目的 locator 溯源是同一套心智，不用额外解释。
3. **它不像 IT 词。** 「文档管理」是采购语言，「卷宗」是干活的人的语言。第一批用户是同类岗位的人，他们看到「卷宗」会对号入座。
4. **`personal-` 前缀保住了你要的语义。** Personal = 文件不出本机 + 只服务一个人 + 五年后还能搬走。这三条是硬约束，不是形容词，已写进 README 第一节。
5. **占用干净。** 2026-11-25 核查：PyPI `personal-dossier` 未注册；GitHub 同名仓库 4 个（均无热度）；`personal-dossier.com` 无 DNS。

---

## 四、被否掉的候选（附原因，避免以后重复讨论）

| 候选 | 否掉的原因 |
|---|---|
| `personal-kb` | 已有同名仓库 `fglirb/personal-kb`（2 star，2026-09-20 后停更）。它是品类词的最强反证：随手搜得到，看完记不住、不 star、不转发。slug 用它等于永远活在别人影子下——但**品类词要保留在 description/topics 里**，那是被搜到的通道 |
| `chinese-doc-rag` | 搜索最强、品牌最弱，读起来像课程仓库；且把范围钉死在「中文」，以后想扩展反而成负担 |
| `docfoundry`（铸造厂） | 隐喻是「工厂/管道」，写给做管道的人；本项目是摆在桌上的东西。品类判断错了，名字必然错 |
| `solutiondesk`（方案台） | 只有角色、没有方法，覆盖不了 PM 场景；且 `desk` 类词 GitHub 撞车 22 个 |
| `docdossier`（卷宗） | 语义同样好，但少了 `personal-`，就要靠 README 补三条硬约束；既然 Personal 是核心约束，让它进名字 |
| `lanben`（蓝本） | 意象好（新方案从旧蓝本长出来），但「蓝本」偏模板，弱化了检索与问答 |
| `deliverable`（交付物） | 语义最准（售前交方案、PM 交计划），但英文太普通，做不成品牌，且 `.com` 已有人用 |
| `presales-kb` | 搜索零竞争、受众一眼对号，但一眼像内部工具，PM 用起来别扭 |
| `cite-ready` / `docrefinery` | 分别撞现有产品 CiteReady 与活跃站点 docrefinery.com |
| `docwright` / `docmint` / `docsift` / `docgate` / `docforge` / `docrag` / `docbench` / `corpuskit` | PyPI 全部已被注册（HTTP 200），无法发布 |

---

## 五、对外三处文案（定稿，直接复制）

### 1. GitHub Description（≤350 字符）

> 售前与项目经理的个人文档知识库：一个客户一卷，把客户给的文件和我方出的方案收进来，问出来每句带出处（PDF 页码 / PPT 页 / 表格行）。文件不出本机，格式不锁定。

### 2. Topics

```
personal-knowledge-base
pkm
document-management
presales
project-management
rag
citation
provenance
local-first
chinese-nlp
docx
xlsx
pptx
pdf
table-extraction
evaluation
```

### 3. README 首屏（已写入 README.md，此处存要点）

```
# 汲古 · 个人文档知识库
> 售前解决方案经理 / 项目经理的个人文档知识库：一个客户一卷，问出来每句带出处。

写方案时最贵的三分钟，是「上次那个类似项目是怎么答的」……

Personal 在这里是三条硬约束：文件不出本机 / 只服务一个人 / 五年后还能搬走
```

首屏必须在前三屏内回答四个问题：**给谁用、解决什么、凭什么信、现在到哪一步**。四者缺一，读者就划走了。

---

## 六、发布清单

- [x] 仓库名占住（public，空仓 + README 首屏）
- [x] description / topics 写入
- [x] LICENSE：代码 Apache-2.0
- [ ] 文档许可 CC BY 4.0 单独标注（手册开始上传时加）
- [ ] `make demo` 用合成语料跑通，再放截图与效果数字
- [ ] 真名脱敏：客户名、项目名、报价数字一律换成合成样本（解析层与评估用例尤其注意）
- [ ] PyPI 占名（第一版可 `pip install` 时再发，占而不用会被清理）
- [ ] homepage 指向 demo 或手册索引页

---

## 七、改名的成本（为什么现在定死）

一旦发布：README 里的自述、issue 里的用户称呼、手册里的 CLI 名、PyPI 包名、别人博客里的链接，五项都要跟着改，且**旧名会永久留在搜索结果里**。
所以名字在发布前定，发布后只在一种情况下改：**定位变了**——比如从「售前/PM 个人工具」改成「团队知识中台」，那本来就该换一个名字，而不是改这个。
