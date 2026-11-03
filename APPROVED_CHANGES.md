# 相对原文的逐项修改对照

主体由原始整理文件直接恢复；每项替换必须精确匹配原文。未列出的原段落和 YAML 文本没有改写或压缩。原文20个阶段提示词和3个子提示词完整保留；六个此前工具补充另存，不作为原文。

本表中的“修改前”用于对照，不是另一套执行规则。来源署名、原文长段及尚未审定的要求保持可见；其他问题等用户系统审阅后再决定。

## 1. 版本与引用说明

修改前：

`````text
## 作者开场
`````

修改后：

`````text
> **版本说明：以原文为主体的逐项修订版。** 原章节、阶段顺序、长篇写作/代码/评审提示词及其详细要求均保留，文末 YAML 完整展开。只改动已确认的内容：方法与实例/环境分开存储、工具按需求选择、安全证明审查、实验必须实际执行、允许有依据地精简、消融酌情使用。未系统审阅的原版数字、循环、目标和其他表述保留供逐项审阅，不代表这些表述已经被验证正确。原作者开场及结语属于来源内容，未核实其出处说法。
>
> **文件对应：** 本文件是主要阅读入口；文末 YAML 的完整内容由 `prompts.yaml` 与 `RESTRICTS.yaml` 提供给本地工具读取，不再用短摘要替代原阶段提示词。原文没有提供的六个阶段提示词在 `prompts-supplement.yaml` 中单独维护，机器读取配置中明确标注为此前新增的工具兼容补充，不能当作原文内容。
>
> **存储对应：** 下文“本文件夹”及相对产物路径指一篇论文实例。题目、摘要、资源、具体方案、参数和正文填入该实例的配置与文档，不填回本通用文件。环境调查、能力需求、选型、配置执行与验证分别记录在实例 `environment/` 和选定环境文件中；主文件只规定方法及引用位置。原目录树的 LaTeX 文件结构保留为可选格式示例，实际格式与路径在实例 `paper/output.yaml` 中选择。
>
> **改动审阅：** [逐项修改对照](APPROVED_CHANGES.md)列出全部替换；[原文差异](original-to-current.diff)可查看增删行。原文长期完整保存在本地 `references/original/整理版.md`，公开对照副本为 [原版整理文件](references/original/整理版.md)。具体实例、环境、密钥和运行记录不在公共仓库中。

## 作者开场
`````

## 2. 工具选择

修改前：

`````text
| D：设计 | 设计实验方案，生成硬件感知的可运行 Python 代码（GPU 等级 → 包选择），估算资源需求 |
`````

修改后：

`````text
| D：设计 | 设计实验方案，根据研究需求和环境调查选择语言/框架，生成可运行实现并估算资源需求 |
`````

## 3. 工具选择

修改前：

`````text
| H：终稿 | 质量门控，知识归档，LaTeX 导出（适配顶会模板），引用完整性 + 相关性核查 |
`````

修改后：

`````text
| H：终稿 | 质量门控，知识归档，按目标格式导出（选择 LaTeX 时适配会议模板），引用完整性 + 相关性核查 |
`````

## 4. 工具选择

修改前：

`````text
| H：稿件 | 22 | EXPORT_PUBLISH | LaTeX |
`````

修改后：

`````text
| H：稿件 | 22 | EXPORT_PUBLISH | 按实例选择的格式导出 |
`````

## 5. 方法与实例/环境分离

修改前：

`````text
- 环境记录：你必须在 PROGRESS.md 中记录每次环境配置的细节，包括安装的库（requirements.txt）、版本号、配置的环境变量等，以保证实验的可复现性和透明度。
`````

修改后：

`````text
- 环境记录：在所属环境记录中保存安装的库、版本号、配置变量名、执行步骤和验证结果；实例 PROGRESS.md 只引用记录位置。实际密钥放在仓库外私密配置，不能进入 Markdown、日志、归档或 Git。
`````

## 6. 方法与实例/环境分离

修改前：

`````text
在当前wsl环境中我配置了如下工具，你可以任意调用它们，并且可以探索还有什么其他工具可以调用，比如duckduckgo之类。
`````

修改后：

`````text
先调查可用接口与工具，按实例研究需求在 environment/requirements.yaml 提出能力要求，在 environment/tools.yaml 记录模型角色、实现和绘图工具的选择依据，并在 environment/plan.md 规划配置及验证。以下变量仅为可选配置字段示例，不表示已经配置或必须使用。实际地址、模型名和凭据留在所属配置中。
`````

## 7. 工具选择与实际执行

修改前：

`````text
实验中你需要调用大模型工具的地方，都可以直接调用这个环境变量中配置的模型接口，保证实验的真实性和可复现性。
`````

修改后：

`````text
实验中需要调用模型时，读取所属私密配置，并记录实际请求参数、版本可得性和调用结果。真实调用是执行证据，不单独保证评价有效性或可复现性。
`````

## 8. 工具选择

修改前：

`````text
可选模型： &lt;模型1&gt;（综合最强，适合大多数任务），&lt;模型2&gt;（稍弱版本），&lt;模型3&gt;（最便宜最快，适合极其简单的任务或大量调用时节省成本），&lt;模型4&gt;（可能适合代码生成相关的实验）。
`````

修改后：

`````text
模型按用途选择：区分写作助手、被评测模型、攻击模型和评判模型；仅启用研究需要的角色。实际模型、版本/接口、参数、预算和限制记录在实例 environment/tools.yaml 及所引用配置。模型裁判需核验可靠性，不能把其判断直接当作安全保证。
`````

## 9. 工具选择与实际执行

修改前：

`````text
写代码方面：你可以调用我命令行的Claude Code工具来写代码，或者可以调用GitHub Copilot CLI（gh）来写代码，使用这种特化工具可能可以提高代码的质量和效率。当然，你也可以尝试自己生成代码，或者直接在本地环境中编写代码，保证代码的真实性和可复现性。
`````

修改后：

`````text
写代码方面：可以自行编写、使用适合的代码助手，或采用经过核对的开源实现和第三方库；具体工具根据研究需要选择并记录。论文中标为本研究实验结果的数据必须来自实际执行，不能把生成代码当作已运行。
`````

## 10. 实验实际执行

修改前：

`````text
真实性：你必须保证论文的数据是你亲自编写代码，或者调用gh（github copilot cli）代码写出来的，具备100%的数据真实性。
`````

修改后：

`````text
真实性：论文中标为本研究实验结果的数据必须来自本项目实际执行过、可追溯的代码或实验流程。代码可以自行编写，也可以使用开源实现、第三方库、工具或远程服务；不能只生成代码或引用示例输出就声称已经运行。公开数据可以作为输入，外部引用、未复现结果与本项目实际运行的结果必须区分。
`````

## 11. 实验实际执行

修改前：

`````text
数据真实性：你必须保证论文中所有实验数据的真实性，所有数据都必须是你亲自编写代码或者调用gh代码写出来的，不能编造数据或者结果。你应该在实验阶段进行充分的测试，保证数据的充足性，并且在结果分析阶段进行合理的对比和解读，确保结论的合理性和严谨性。
`````

修改后：

`````text
数据真实性：你必须保证论文中所有实验数据的真实性。本研究实验结果必须来自本项目实际执行过的代码或实验流程，不要求代码全部由自己编写；保存代码/工具版本、输入来源、参数、运行命令或调用记录、时间和原始输出，不能编造数据或结果。你应该在实验阶段进行充分的测试，保证数据的充足性，并且在结果分析阶段进行合理的对比和解读，确保结论的合理性和严谨性。外部引用、理论估算和未执行计划必须分别标明。
`````

## 12. 工具选择

修改前：

`````text
你必须使用 &lt;目标会议名称&gt; 的 LaTeX 模板来撰写论文，模板文件已经放在/paper/&lt;目标会议模板文件夹&gt;目录下。你需要按照模板的要求来组织论文的结构和格式，确保论文符合 &lt;目标会议名称&gt; 的投稿规范。
`````

修改后：

`````text
你必须遵守 &lt;目标会议名称&gt; 的投稿规范；编辑与输出工具由目标要求和研究需要决定，在实例 paper/output.yaml 记录选择依据、源文件及交付路径。选择 LaTeX 时，使用对应官方模板并在/paper/&lt;目标会议模板文件夹&gt;维护其来源和版本；不假定模板已经存在。
`````

## 13. 工具选择

修改前：

`````text
你应该在/paper/mypaper目录下撰写你的论文，主文件为main.tex，你可以在sections目录下创建不同的tex文件来撰写论文的不同部分（如：introduction.tex、methodology.tex、experiments.tex、related_work.tex等），并在main.tex中通过\\input{sections/introduction.tex}等命令来组织这些部分。
`````

修改后：

`````text
你应该在/paper/mypaper目录下组织论文材料，具体源文件和输出路径以 paper/output.yaml 为准。若选择 LaTeX，主文件可为main.tex，可以在sections目录下创建不同的tex文件来撰写不同部分（如introduction.tex、methodology.tex、experiments.tex、related_work.tex等），并通过\\input{sections/introduction.tex}等命令组织这些部分；其他格式采用对应的可编辑结构。
`````

## 14. 工具选择

修改前：

`````text
你应该在论文中合理地引用你在文献调研阶段找到的相关工作，确保引用的格式符合 LaTeX 的规范，并且在&lt;会议缩写&gt;.bib文件中维护好你的参考文献列表。
`````

修改后：

`````text
你应该在论文中合理地引用在文献调研阶段找到的相关工作，确保引用符合目标格式；选择 LaTeX 时在&lt;会议缩写&gt;.bib中维护参考文献，其他格式使用对应的引用管理方式。
`````

## 15. 工具选择

修改前：

`````text
不同的tex放在不同的文件里，保证结构清晰，便于修改和维护。
`````

修改后：

`````text
各部分按所选格式分文件或分章节组织，保证结构清晰，便于修改和维护；选择 LaTeX 时不同的tex放在不同文件里。
`````

## 16. 工具选择

修改前：

`````text
论文配图部分，你应该在tex中用注释留下一段严格的prompt，后面我会把prompt给nano banana 2进行绘图。
`````

修改后：

`````text
论文配图应保留可编辑来源和制作说明。协议图、结构图优先采用能准确表达并核对符号与流程的方式；概念插图可按需要使用生成式图片，但不固定模型或服务，也不以此替代精确协议描述。说明可放在所选文稿格式的注释或图表文件中。
`````

## 17. 工具选择

修改前：

`````text
图表类可以直接调用python进行绘图，使用matplotlib、seaborn等库来生成，保证图表的清晰度和专业性。
`````

修改后：

`````text
统计图必须来自真实数据，保留输入、转换和绘图来源；绘图库与工具按需求选择并在实例 environment/tools.yaml 记录，不统一指定 Python 或某个绘图库。保证图表清晰、可核对。
`````

## 18. 工具选择

修改前：

`````text
真实数学逻辑： 必须使用 NumPy 矩阵运算实现真实的算法（如手动实现梯度计算或基于真实数据的交叉熵）。
`````

修改后：

`````text
真实数学逻辑：必须实现符合研究对象的真实算法或协议，不统一指定 NumPy 或编程语言。根据实例方案选择工具并说明实现属于功能原型、仿真还是实际实现；记录包含和省略的操作，不把忽略密码学操作、通信、序列化或网络等待的原型测量直接外推为实际协议性能。
`````

## 19. 工具选择

修改前：

`````text
Figure 1 霸权： 必须在初稿前构思好“图 1”。图 1 必须能独立传达这篇论文的最核心贡献，并在 prompt 中为 Nano Banana 2 提供极为详尽的视觉元素描述。
`````

修改后：

`````text
Figure 1 霸权：必须在初稿前构思好“图 1”。图 1 必须能独立传达这篇论文的最核心贡献；根据图的性质选择制作方式，并保留可编辑来源或详尽制作说明，不固定使用某个生成式绘图模型。
`````

## 20. 酌情消融

修改前：

`````text
强制消融实验 (Ablations)： 论文中提到的任何“有效组件”，代码中必须包含且论文中必须报告“移除该组件”后的对比数据。没有消融实验，直接拒绝进入下一步。
`````

修改后：

`````text
消融实验 (Ablations)：根据研究问题判断是否必要、是否具备有效比较条件，适用时报告组件移除、替代或控制后的对比。没有必要或没有有效条件时可以不做，记录理由和支撑主张的其他证据。移除必要安全或正确性组件所得的退化版本不能作为同等条件的有效基线；不得仅因没有消融而直接拒绝下一阶段。
`````

## 21. 工具选择

修改前：

`````text
沙盒依赖： 优先使用 Python stdlib, numpy, math, statistics。在非必要情况下（即纯算法创新时），禁止强行引入庞大的深度学习框架。
`````

修改后：

`````text
依赖与隔离：根据研究对象、正确性、安全性和复现需求选择语言、库及运行环境，不统一限制为 Python/NumPy，也不强制采用深度学习框架。具体依赖、隔离方式和验证记录存入所属环境文件。
`````

## 22. 工具选择

修改前：

`````text
NumPy 2.x 强制兼容 (CRITICAL)：
`````

修改后：

`````text
原文 NumPy 兼容性备注（仅在选择该库时作为历史参考，按实际版本验证；不作为所有研究的强制选型）：
`````

## 23. 安全证明与允许精简

修改前：

`````text
## YAML 配置（排版恢复）
`````

修改后：

`````text
### 安全性证明审查（已确认新增，关联 8.5、18、20、24 阶段）

涉及安全性主张时，明确命题、安全定义、参数、对手能力、基础假设和适用范围。在实例 docs/security_proof.md 保存所依赖的引理/定理与出处、证明步骤及依赖关系；采用归约、模拟或混合论证时说明构造、分布关系、优势界与失败概率等适用要素。核对证明前提与协议及实际实现是否一致。

标明待证明、猜想、证明草图、完整推导待复核、已复核或有缺口，并记录复核范围与未解决问题。模型评分、程序运行成功或未观察到攻击不能替代安全证明；经验评测必须限定结论范围，不冒充形式化保证。需要哪些安全假设按研究对象确定，具体值只写入实例文件。

### 修订长度（已确认修改）

允许扩写、删减、合并和重组，不要求修订稿比初稿更长。避免无说明地把完整稿缩成摘要或丢失关键定义、论证、证据、证明前提与局限；重要删减记录理由和去向，错误、重复、无关或无依据内容可删除或更正。原文其他篇幅建议保留供审阅，不据此新增“只能增加不能减少”的要求。

## YAML 配置（原长提示词，按已确认条目修订）
`````

## 24. 工具选择

修改前：

`````text
Always use the ```filename:xxx.py format for each file. Use numpy for numerical computation. Keep code self-contained and deterministic.
`````

修改后：

`````text
Use the selected implementation language and its appropriate file format. Record dependencies and reproducibility conditions; Python/NumPy below is an optional implementation example, not a required toolchain. Keep execution records for results actually obtained.
`````

## 25. 工具选择

修改前：

`````text
      Generate a Python experiment project for the following research topic:
`````

修改后：

`````text
      Generate an experiment implementation for the following research topic using the tools selected in environment/tools.yaml:
      The Python/NumPy optimization instructions and file examples below apply only when that implementation is suitable. Adapt tool-specific language, file formats, data/network/GPU access and stopping checks to the approved research plan; preserve genuine execution, metrics and traceability. A functional prototype or simulation must not be presented as a full protocol implementation.
`````

## 26. 工具选择与实际执行

修改前：

`````text
      - No external data files, no network calls, no GPU required
      - FORBIDDEN: subprocess, os.system, eval, exec, shutil, socket
`````

修改后：

`````text
      - Data files, network calls, GPU and process/communication tools are selected and recorded in the experiment and environment plans; do not assume they are available or unnecessary.
      - Record actual executions and inputs/outputs; generated code alone is not experimental evidence.
`````

## 27. 工具选择

修改前：

`````text
      NUMPY 2.x COMPATIBILITY (CRITICAL):
`````

修改后：

`````text
      NUMPY COMPATIBILITY NOTES (optional historical example; verify against the selected version):
`````

## 28. 酌情消融

修改前：

`````text
      Required keys: objectives,datasets,baselines,proposed_methods,ablations,metrics,risks,compute_budget.
`````

修改后：

`````text
      Required keys: objectives,datasets,baselines,proposed_methods,ablations,metrics,risks,compute_budget.
      In ablations, record necessity and valid comparison conditions. If not needed or not applicable, state reasons and alternative supporting evidence; do not treat an incorrect or insecure variant as an equivalent baseline.
`````

## 29. 工具选择

修改前：

`````text
      Format revised paper into clean final markdown for publication export.
`````

修改后：

`````text
      Format revised paper for the output format and paths selected in paper/output.yaml; use a verified tool or record a missing capability rather than assume conversion is available.
`````

## 30. 酌情消融

修改前：

`````text
      5. ABLATIONS: Remove one component at a time and measure the effect. Without ablations, reviewers cannot tell which parts matter.
`````

修改后：

`````text
      5. ABLATIONS: When necessary and meaningful, remove, replace or control components and measure the effect. If not applicable, explain why and provide suitable evidence for the claim; removing required security or correctness components need not yield a valid baseline.
`````

## 31. 酌情消融

修改前：

`````text
      - Missing ablations: systematically demonstrate each component's contribution
`````

修改后：

`````text
      - Unsupported component claims: use applicable ablations or other appropriate evidence; justified non-applicability is not automatically a rejection reason
`````

## 32. 实验实际执行

修改前：

`````text
      You ONLY use real experimental data — never fabricate or approximate numbers. Every metric value must exactly match the provided experiment output.
`````

修改后：

`````text
      Results presented as this study's experiments MUST come from code or experimental workflows actually executed for this project, including suitable open-source implementations and third-party tools. Preserve versions, inputs, parameters, execution logs and raw outputs. Label cited/unreproduced results and theoretical estimates separately; public datasets may be inputs. Do not fabricate values; summaries, conversions and rounding must be traceable to actual outputs.
`````

## 33. 工具选择

修改前：

`````text
      Write a FULL-LENGTH paper draft section by section in markdown.
`````

修改后：

`````text
      Write a FULL-LENGTH paper draft section by section in the editable format selected in paper/output.yaml.
`````

## 34. 酌情消融

修改前：

`````text
statistical significance discussion, ablation studies, qualitative analysis where relevant
`````

修改后：

`````text
statistical significance discussion, ablation studies where necessary and valid (otherwise explain non-applicability and supporting evidence), qualitative analysis where relevant
`````

## 35. 工具选择

修改前：

`````text
Results tables should use markdown table format with proper column headers
`````

修改后：

`````text
Results tables should use the selected document format with proper column headers
`````

## 36. 允许精简

修改前：

`````text
When revising, NEVER shorten existing sections — only expand, improve, and add content. The final paper must be at least as long as the draft.
`````

修改后：

`````text
When revising, allow expansion, deletion, consolidation and reorganization. Do not silently turn a full paper into a summary or lose essential arguments, evidence, proof assumptions or limitations. Record reasons for substantial cuts; remove or correct unsupported, incorrect or redundant content. The final paper need not be longer than the draft.
`````

## 37. 允许精简

修改前：

`````text
      CRITICAL: Maintain or INCREASE the paper length. Each section must meet its minimum word count:
`````

修改后：

`````text
      CRITICAL: Preserve the necessary argument and evidence, not the previous length. Apply the instance's actual requirements and record substantial cuts. Original section-length guidance retained for review:
`````

## 38. 允许精简与工具选择

修改前：

`````text
      Return revised markdown only.
`````

修改后：

`````text
      Return the revised paper in the selected editable format; record significant changes and their reasons in docs/paper_revision.md.
`````

## 39. 酌情消融

修改前：

`````text
Are ablation studies present and meaningful?
`````

修改后：

`````text
Are ablations necessary and valid here? If applicable, are they meaningful? If not, are the reason and alternative supporting evidence clear?
`````

## 40. 安全证明与实际执行

修改前：

`````text
      Paper draft:
      {draft}
      {experiment_evidence}
`````

修改后：

`````text
      6. SECURITY CLAIMS: Read docs/security_proof.md when applicable. Check definitions, assumptions, proof dependencies and steps, status/gaps, review scope and correspondence to the implementation. Distinguish empirical evaluations from formal guarantees; tests or model scores are not proofs.
      7. EXECUTION EVIDENCE: Verify which results were actually executed for this project, which are cited and unreproduced, and which are estimates or plans. Reused code is allowed; preserve provenance and raw outputs.
      Paper draft:
      {draft}
      {experiment_evidence}
`````

## 41. 工具选择

修改前：

`````text
      IMPORTANT: Do NOT use subprocess, os.system, eval, exec, or any network/shell calls.
`````

修改后：

`````text
      IMPORTANT: Use only the process, network and tool capabilities selected for this experiment and its environment; do not assume a universal tool prohibition. Record changes and actual verification.
`````

## 42. 工具选择

修改前：

`````text
      Do not use subprocess, os.system, eval, exec, or any network/shell calls.
`````

修改后：

`````text
      Use only process, network and tool capabilities selected for this experiment and its environment; preserve their documented constraints.
`````
