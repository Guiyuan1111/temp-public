> **原文标题**：From Prompt to Clone: Copyright Challenges in AI Model Distillation（从提示词到克隆：AI 模型蒸馏中的版权法挑战）
> **作者**：Claudia Philipp
> **出处**：17 UC Law SF Sci. & Tech. Just. L.J. 49 (2026)（UC Law Science and Technology Journal，第 17 卷第 1 期第 3 篇论文，2026 年冬季号，第 49–82 页）
> **原文链接**：<https://repository.uclawsf.edu/hastings_science_technology_law_journal/vol17/iss1/3>
> **译文说明**：本文档系英文原文之完整中文译文，中文译文仅供参考，理解与引用请以英文原文为准。

# 从提示词到克隆：AI 模型蒸馏中的版权法挑战

*From Prompt to Clone: Copyright Challenges in AI Model Distillation*

**作者致谢脚注（\*）**：笔者谨向 Robin Feldman 教授在整个研究过程中给予的宝贵指导致以诚挚谢意，并感谢 Helen Nguyen 及《科学技术法律期刊》（STLJ）团队勤勉的工作与协助。同时，谨以此文献给我的家人——Kathy、TZ 与 Ross——是他们坚定不移的支持使这项工作得以完成。

## 摘要（ABSTRACT）

本文探讨模型蒸馏（model distillation）在大语言模型（large language models, LLMs）语境下的合法性问题——在这一过程中，较小的“学生模型”（student model）通过模仿较大的专有“教师模型”（teacher model）的输出而完成训练。随着人工智能持续高速发展，围绕专利法与合同法的法律框架正经受考验。本文具体考察：现行美国版权法是否为前沿 LLM 开发者提供了充分保护，以及未经授权的蒸馏之类行为是否构成侵权。通过在现行法律学说——包括合理使用（fair use）、使用条款的执行力以及近期诉讼——之下分析模型架构、训练数据、行为模仿与逆向工程，本文发现：依现行法律，模型蒸馏不太可能构成版权侵权。尽管如此，这一做法对创新、专有模型保护以及开源伦理所引发的更广泛影响表明，对人工智能开发中的知识产权规范进行重新审视，既属必要，亦已迫在眉睫。

## 目录（TABLE OF CONTENTS）

- 概述（Overview）
- 大语言模型发展与模型蒸馏导论（Introduction to Large Language Model Development and Model Distillation）
  - A. 大语言模型的发展（The Development of LLMs）
  - B. 模型蒸馏简介（Introduction to Model Distillation）
  - C. 模型蒸馏的实例（Examples of Model Distillation）
- I. 大语言模型如何融入现行版权法框架（How LLMs Fit into the Current Copyright Framework）
  - A. 现行版权法框架（Existing Copyright Framework）
    - i. 训练源代码（Training Source Code）
    - ii. 训练数据（Training Data）
    - iii. 生成模式（Generated Modes）
- II. 模型蒸馏是否构成版权侵权？（Is Model Distillation Copyright Infringement?）
  - A. 训练数据的利用（Utilization of Training Data）
  - B. 模仿教师模型行为（Mimicking Teacher Behavior）
  - C. 经由逆向工程的（非）直接复制（(In)Direct Copying via Reverse Engineering）
  - D. 抗辩（Defenses）
- III. 针对模型蒸馏的替代性保护（Alternative Protections Against Model Distillation）
  - A. 专利（Patents）
  - B. 使用条款（Terms of Use）
- IV. 变革的可能性与开源需求的兴起（Potential for Change and The Rise in Demand for Open-Sourcing）
  - A. 版权框架是否应当修改？（Should the Copyright Framework be Altered?）
  - B. 开源的呼吁（The Call for Open-Sourcing）
- 结论（Conclusion）

## 概述（OVERVIEW）

面对大语言模型（LLMs）算力消耗巨大、环境成本高昂所引发的日益关切，模型蒸馏（model distillation）已成为一项关键技术，能够把强大的教师模型压缩为更高效的学生模型。这一过程在带来巨大实用价值的同时，也引发了法律与伦理上的争议。本文所要解决的核心问题是：模型蒸馏——尤其是在未经原始模型创建者同意的情况下实施时——是否构成版权侵权或其他违反知识产权法的行为。本文首先阐释 LLM 背后的架构与训练过程，包括数据整理（data curation）、词元化（tokenization）与转换器（transformer）设计；继而介绍模型蒸馏，描述较小的模型如何通过收集并学习较大模型的输出来模仿其行为。文章探讨了三个潜在的法律关切领域：受版权保护训练数据的使用、对表达性行为的模仿，以及经由提示词探测（prompt probing）之类技术对模型结构的逆向工程（reverse engineering）。

通过判例法分析——包括 Google 诉 Oracle 案（Google LLC v. Oracle America, Inc.）、索尼诉 Connectix 案（Sony v. Connectix）以及《纽约时报》诉 OpenAI 案（New York Times v. OpenAI）——本文评估了版权以及使用条款等合同性工具在保护 LLM 方面的优势与不足。文章还考察了专利保护的可行性，并讨论了 AI 社区中日益高涨的开源运动。分析表明，现行版权法无力保护人工智能的功能性、行为性与算法性要素；合理使用、逆向工程学说以及模型输出薄弱的可版权性，往往都不利于前沿实验室提出侵权主张。鉴于技术的快速演进，现行版权框架愈发显得无力跟上创新的步伐，在不久的将来很可能需要重大改革，方能保持其效力与相关性。

## 大语言模型发展与模型蒸馏导论（INTRODUCTION TO LARGE LANGUAGE MODEL DEVELOPMENT AND MODEL DISTILLATION）

近年来，大语言模型（LLMs）在广泛的自然语言处理任务中展现出卓越的能力。然而，其不断增长的规模与算力需求，使其在资源受限环境中的部署面临重大挑战。[^1] 模型蒸馏作为一种前景可期的解决方案应运而生：它能够在不明显损失性能的前提下，把知识从庞大而复杂的“教师模型”（teacher model）迁移至更小、更高效的“学生模型”（student model）。[^2] 然而，这一技术进步正在使现行知识产权框架趋于紧张，如何判定学生模型开发者的行为是否构成侵权，由此成为一个难题。

模型蒸馏的核心在于“一个模型教另一个模型”的原则——即把知识从大型预训练的教师模型迁移至更为紧凑、高效的学生的过程。[^3] 这项机器学习技术使开发者能够在大幅降低计算成本与复杂性的同时，保留原始模型的大部分性能。[^4] 学生模型通常被设计得更快、更小、更经济，因而更适合在现实应用中部署。[^5] 但要实现这一点，需要海量训练数据——往往达数百 GB——并通过 Common Crawl、Octoparse、Scrapy 等大规模网络抓取工具获取。[^6] 然而，LLM 并不仅仅是其训练所用数据的集合。其能力不仅源于庞大的训练语料库，也源于底层的转换器架构以及深度神经网络设计的进步。[^7] 这一复杂问题的核心在于：现行法律对 LLM 提供了何种保护，以及这些保护是否——或如何——延伸至建立在更大的前沿“教师模型”基础框架之上的学生模型。

蒸馏模型并非只是在静态数据集上训练而成；相反，它们往往是通过接触前沿模型的输出而得以优化的。[^8] 实际上，学生模型是通过模仿原始教师模型的输出来学习，而非直接从底层数据中学习。因此，可版权性问题可能较少取决于传统意义上的数据复制，而更多取决于：模仿表达性要素——诸如输出的风格、语气或结构——是否构成一种受保护的表达。在此背景下，诸如《纽约时报》诉微软等被告案（New York Times v. Microsoft et al.）——该案涉及受保护新闻内容的再利用——的裁判结果，对于判定 LLM 的行为享有哪些基础性保护，可能极具参考价值。[^9]

尚待回答的问题是：究竟存在哪些法律保护来捍卫前沿 AI 实验室，而面对蒸馏风险，这些保护又能否提供足够的激励，使其得以继续创新。与此同时，其中许多实验室又在力推开源模型，以期激发创业活力、加速 AI 领域的发现，而这可能削弱、甚至放弃其本可主张的部分知识产权。

本文并不试图解决 LLM 自身的训练或运行是否构成版权侵权的问题——这一问题正由诸如微软以及 Thomson Reuters Enterprise Centre GmbH 诉 ROSS Intelligence Inc. 案（Thomson Reuters Enterprise Centre GmbH v. ROSS Intelligence Inc.）等案件加以检验——而是聚焦于：把这些模型蒸馏为更小的派生性“学生模型”，是否构成、或是否应当构成版权侵权。[^10]

### A. 大语言模型的发展（The Development of LLMs）

开发 LLM 的第一步是整理数据。这迄今为止是构建 LLM 过程中最重要、也最耗时的环节，因为模型的质量在很大程度上取决于数据的质量。[^11] 数据的获取有多种不同方法。一些公司利用公开数据集、私有数据源，甚至使用其他 LLM 模型来生成数据。[^12] 版权问题上的主要担忧正是由此产生。数据获取完成后，还必须对数据进行清洗。这包含多个步骤：质量过滤、去重、隐私信息删除、规范化，以及把数据转换为词元（token）。[^13] 词元本质上是“把大块信息拆分后得到的微小数据单元”，其目的在于让模型能够更有效地分析提示词（prompt）所请求的内容。[^14] 用更简单的话说：当你面对一个庞大的数据池时，每一条数据都需要被拆解为其组成元素，这一过程称为 LLM 分词（tokenization）；这些元素就是所谓的“词元”。

分词可以发生在整词层面（如“apple”），也可以发生在子词层面。例如，单词“unhappiness”可以被拆分为“un”和“happi”，正如英语单词往往由前缀与词干构成那样。通过子词分词（subword tokenization），模型可以把新遇到的、未见过的词拆解为熟悉的组成部分来处理。[^15] 这一方法对于词形结构复杂或形态丰富的语言尤其有用，因为在这类语言中整词分词的效率较低。[^16]

完成分词之后，这些词元会被赋予数值，模型据此理解并生成回应。[^17] 分词过程使模型能够高效处理海量文本，并生成连贯、有意义的输出。为便于理解：“语言模型的基本前提，是它能够根据迄今观察到的文本，预测下一个单词或子词（称为词元）。”[^18] 按平均值计，每三个单词会被转换为四个词元。[^19]

分词过程的整体本身并不归 LLM 训练者享有版权，因为他们使用的很可能是既有的算法。[^20] 许多公司开发自己专有的分词算法与系统，以支撑 LLM 的训练。在这些情形下，如果公司取得了第三方专有分词技术的许可，或使用了包含分词功能的软件框架，便可能通过许可协议为该使用付费。[^21] 例如，如果公司使用第三方的商业分词工具或软件包（如专门的 NLP 库或工具包），便可能在特定许可条款下为其使用权付费。[^22] 一些公司则使用向公众免费开放的开源分词系统。[^23] 诸如 Hugging Face 的 tokenizers 或 SpaCy 等流行库将分词作为其工具集的一部分提供，可以在开源许可证（如 MIT 许可证）下免费使用。[^24] 公司也可以选择使用把分词作为 LLM 训练流水线组成部分的云端服务，例如 Google Cloud AI、Microsoft Azure Cognitive Services 或 Amazon AWS 所提供的服务。在这些情形下，公司按使用量付费，例如按 API 调用次数、算力或处理的数据量计费。[^25] 例如，一些平台提供公司可直接使用的预构建 LLM 及配套分词功能，其费用会随使用规模持续产生。[^26]

第二步是创建模型架构。LLM 模型架构主要建立在转换器（transformer）架构之上。在 LLM 语境下，转换器是一组由编码器与解码器组成、具备自注意力（self-attention）能力的神经网络。转换器是一种深度学习架构，已成为绝大多数现代 AI 语言模型的基础。[^27] 它处理数据序列，并使用一种被称为自注意力的机制[^28]来理解输入各部分之间的关系，从而无需逐词处理便能把握上下文、语义与语序。转换器能够理解长篇幅文本中的上下文，且用途灵活，可用于文本生成、翻译、摘要等多种任务。[^29] 如果把 LLM 比作一座摩天大楼——其中满是语言与层层楼面——那么转换器就是这座大楼赖以建造的地基。模型架构创建完成后，机器学习生命周期会经历若干关键阶段。第一阶段是数据管理，包括为训练与验证获取并准备数据集——涵盖数据收集、预处理（如标注）与数据增强。[^30] 第二阶段是模型学习，重点在于通过算法选择、超参数调优与迭代训练，从训练数据中合成机器学习组件。[^31] 第三阶段是模型验证，通过评估与测试确保训练后的模型满足预期要求，这一步在安全敏感的应用中尤为关键。[^32] 最后是模型部署阶段，把通过验证的模型集成到完整系统之中，投入真实环境运行并持续监控。[^33]

### B. 模型蒸馏简介（Introduction to Model Distillation）

对一个既有语言模型进行蒸馏，意味着把知识从一个庞大而强大的模型（“教师”）迁移到一个更小、更高效的模型（“学生”）。[^34] 教师模型通常是最先进的系统，它依托大量计算资源在海量数据集上训练而成，因而是一座语言与上下文知识的宝库。[^35] 其目标是让学生模型通过模仿教师的行为、内化其输出中的模式来向教师学习。这一过程可以在不直接接触教师模型权重或架构的情况下进行，而是依托其应用程序编程接口（application programming interface, API）。[^36] API 是一种结构化的方法，开发者借以向教师模型发送输入（提示词）并接收输出，而不会暴露模型的底层结构。[^37] 这种安排使“黑盒蒸馏”（black-box distillation）成为可能——学生完全从教师可观察到的输入—输出行为中学习。[^38]

学生模型的训练采用一种称为“模型模仿”（model imitation）或“零样本蒸馏”（zero-shot distillation）的技术：学生模型学习在广泛的问题上复现教师的输出。[^39] 这通过大规模收集训练数据来实现：开发者以多样化的提示词系统地查询 API，并用返回的回应——即所谓“软目标”（soft targets）——来训练学生模型。其结果是一个紧凑而计算高效的模型，它在逼近原初高资源教师模型性能的同时，又适合部署于对速度和资源限制敏感的现实应用。

这通常是一个两步训练过程：第一步模仿教师，第二步基于真实数据进行微调（fine-tuning）。[^40] 在蒸馏过程中，学生模型观察教师对各种输入的预测与回应。教师模型被输入无标注数据，并依据其预测生成标签或回应。蒸馏过程中使用两类标签：“硬标签”（hard labels）与“软目标”。[^41] 硬标签是直白、具体的标签，给出确定性的答案，例如某个特定的类别或输出。与之相对，软目标则是所有可能输出之上的概率分布，能够更细致地反映教师模型的预测。[^42]

在蒸馏过程中，学生模型使用教师的软目标进行训练。这些软目标比硬标签提供更详尽的信息：它们不仅指出最可能的输出，还给出其他可能输出的相对可能性。[^43] 例如，当被问及“德国的首都是哪里？”时，教师模型可能输出：

- 柏林：99%
- 慕尼黑：0.5%
- 法兰克福：0.4%
- 其他城市：0.1%

通过利用这些软目标，学生模型不仅了解到柏林是最可能的答案，还领会了教师对其他可能性的置信程度。这有助于学生模型更好地捕捉教师决策过程中的深层模式与不确定性，从而提升其在各类输入上的泛化能力。为了让教师的软目标蕴含更多信息，人们会使用一种称为温度缩放（temperature scaling）的技术。[^44] 温度缩放调整模型输出函数中的“温度”参数：

- 低温：输出尖锐而自信（例如“柏林”占 99%）。
- 高温：输出被软化，概率分布在各个合理选项之间（例如“柏林”占 80%、“慕尼黑”占 10%、“法兰克福”占 5%）。

如此软化输出，有助于学生模型更好地理解教师的推理过程，尤其是在正确答案并不显而易见的情形下。它使学生不仅学到正确答案，还学到教师为何认为其他答案也有道理，从而提升其泛化能力。[^45]

这些回应便构成用于训练学生模型的“人工标注”数据。学生模型的任务是从这些数据中学习，模仿教师的行为并内化其知识。[^46] 它不仅从教师的直接输出中学习，也从教师在不同情境下如何调整回应之中学习。这有助于学生模型把握语言的细微之处，尽管其参数更少、所需算力也更低。蒸馏的难点在于：在缩小学生模型的规模与复杂度、使其更适用于现实应用的同时，保持教师模型的准确性与性能。

教师模型与学生模型的主要结构差异在于：教师模型通常拥有数千亿个参数，并通过强化学习（reinforcement learning）等先进方法训练而成；[^47] 而学生模型通常仅以 10 亿至 700 亿个参数、在蒸馏输出上以监督学习（supervised learning）方式训练，往往依赖捷径而非完整的逻辑过程。简而言之：对法学院学生而言，这就像依赖 Quimbee 的案例摘要而非阅读判决全文；对非法律专业的学生而言，这就像依赖一本书的 SparkNotes 版本而非阅读原著。这种压缩不可避免的结果，是细节的丢弃、推理的简化和边缘情形的遗漏——最终导致细腻度与深度的损失。例如，学生模型可能学会“12 × 5 = 60”这一简单的等式，却并未真正理解等式背后的算术逻辑。[^48] 此外，其面向特定任务的优化在某些方面可能是有利的；然而，为了优先保证速度与规模，“教师[模型]的某些功能被排除在外”。[^49]

然而，蒸馏模型的创建仍有其益处。“蒸馏后的 LLM 生成预测的速度快得多，所需计算资源与环境资源也少于完整的 LLM。”[^50] 它耗费的时间、能源与资源更少。LLM 蒸馏被用作规避高昂成本、提升速度、免去为协调大量资源而带来的基础设施麻烦的手段。[^51] 这类模型非常适合某些狭窄任务、移动应用或实时系统。[^52]
### C. 模型蒸馏的实例（Examples of Model Distillation）

蒸馏既可以在获得授权的情况下进行，也可以未经授权进行。获得授权的蒸馏，就是指教师模型的开发者明确授权学生模型的开发者。而未经授权的蒸馏，通常是指开发者以一种可能违反该模型使用条款（terms of use）的方式与专有模型交互。[^53] 包括 OpenAI、Google 和 Anthropic 在内的大多数商业 AI 提供商，都在其使用条款中明确禁止此类行为。[^54] 这些条款一般禁止利用其模型的输出训练竞争性模型，即使相关数据是公开可得的。[^55]

迄今为止，关于“未经授权”模型蒸馏最著名的案例研究，是 DeepSeek 于 2025 年 1 月 20 日发布的 R1。[^56] DeepSeek 是一家中国的 AI 研究实验室，其公开承认使用蒸馏技术开发了 R1——一个足以比肩 OpenAI、Google DeepMind 等业界巨头系统的强大 LLM——并因此登上各大媒体头条。[^57] 模型蒸馏虽是机器学习领域早已确立的实践，但 DeepSeek 的做法——以及 R1 卓越的效果——还是在 AI 社区引发了强烈震动。[^58]

DeepSeek 利用了知识蒸馏（knowledge distillation）这一传统上用于使 AI 模型更小、更高效的技术。然而，DeepSeek 并未蒸馏自己的专有模型，而是从一个外部的、更强大的 AI 系统——据信是 OpenAI 的 GPT-5 或类似的先进闭源模型——中提取知识。[^59] DeepSeek 的团队系统地与一个最先进的 AI 模型交互，很可能是通过 API 访问。他们必须生成数以百万计的查询，涵盖推理、编程、创意写作与问题求解等广泛任务。通过收集这些回应，他们在理论上构建了一个由高质量训练样本组成的庞大数据集。[^60] 在汇集了 AI 生成的回应数据集之后，DeepSeek 对数据进行了整理与结构化，过滤掉不一致之处并确保连贯性。[^61] 这使他们不仅捕捉到了事实性信息，还捕捉到了先进模型组织答案方式的底层模式。[^62] DeepSeek 利用这个从外部 AI 蒸馏而来的数据集，通过模仿学习（imitation learning）训练了 R1——所谓模仿学习，即模型通过模仿另一个系统的行为来学习。[^63] 与以人工标注数据训练模型的传统监督学习不同，这种方法把一个先进 AI 的知识直接迁移到了一个新系统之中。

完成初始训练后，DeepSeek 又运用强化学习以及额外的开源数据集对 R1 进行微调，以提升其性能。[^64] 这一步骤使他们得以打磨蒸馏模型较弱的环节，并填补最初提取过程中留下的知识空白。蒸馏的一大优势在于，它造就的模型比原模型更小、更快、运行成本更低。DeepSeek 对 R1 进行了优化，使其在算力需求显著降低的情况下，达到与前沿模型接近相当的水平。[^65]

DeepSeek 的方法并不违法，但它动摇了专有式 AI 开发的根基。OpenAI、Google 等公司在训练其 AI 模型上投入数十亿美元，依赖云基础设施、专有数据集与尖端研究。[^66] DeepSeek 的蒸馏方法绕开了其中的大部分成本——他们并非从零构建最先进的模型，而是有效地对一个既有系统的知识进行了逆向工程。[^67] AI 行业很快意识到了更深层的影响。如果蒸馏行为不受约束，较小的实验室与初创企业便能以少得多的资源，复制价值数十亿美元的 AI 模型的能力。领先的 AI 公司可能需要开发新的安全措施来防止未经授权的蒸馏，例如 API 限制，或使提取有用训练数据变得更加困难的密码学技术。基于蒸馏的模型的兴起，还可能助推开源 AI 开发的新浪潮，挑战专有式 AI 实验室的主导地位。

DeepSeek 的举动引起了政策制定者的注意。新任美国 AI 与加密货币事务负责人（AI and Crypto Czar）David Sacks 谈及此事时表示，有“实质性证据”表明模型蒸馏被用于复制领先的 AI 系统。[^68] Sacks 认为，领先的 AI 公司必然会采取措施防范蒸馏，从而拖慢部分“模仿者模型”（copycat models）的脚步。[^69] 作为回应，一些 AI 实验室开始实施更严格的 API 限制，使外部各方难以对其模型进行大批量查询。[^70] 另一些实验室则探索技术性对策，例如在 AI 生成的输出中嵌入水印，以追踪其是否被用于蒸馏。[^71] 然而，DeepSeek 的 R1 证明这些对策尚非万无一失。

DeepSeek R1 案点燃了一场紧迫的辩论：AI 公司应当专注于技术防护措施——例如防止大规模查询、在回应中嵌入密码学水印——还是应当诉诸法律执行，例如出台覆盖从 AI 模型中提取知识的新知识产权保护？在 AI 公司与政策制定者苦苦权衡这些问题之际，有一点是明确的：模型蒸馏不再只是一种研究工具——它是一股足以重塑人工智能竞争格局的颠覆性力量。此外，它也引出了这样一个问题：对于前沿实验室而言，如今存在哪些保护措施，又可能存在哪些保护措施？

## I. 大语言模型如何融入现行版权法框架（HOW LLMS FIT INTO THE CURRENT COPYRIGHT FRAMEWORK）

根据美国宪法专利与版权条款以及后来的 1975 年《版权法》（the Copyright Act of 1975）所确立的普遍共识，版权法只保护由人类创作的原创作品。[^72] 虽然该框架可能进一步涵盖借助 AI 辅助完成的作品，但完全由非人类创作和生成的作品不受保护。[^73] 法院一贯认为“人类创作（human authorship）是版权的基石性要求”，并由此暗示：人工智能、LLM 以及任何类似事物均不具备原创创作的能力。[^74] 然而，与此同时，创建了该 AI 或 LLM 的作者，之后也无法对该 AI 所创作的内容保留版权。正如《版权登记指南》（Copyright Registration Guidance）所言：“如果作品的传统创作性要素由机器生成，该作品便缺乏人类创作，版权局将不会对其予以登记。”[^75] 这表明，对于创作投入被层层稀释的作品而言，其所能获得的保护是有限度的。这种保护以原创主义（originalism）理论为中心，即版权在本质上旨在保护原创作品。独创性（originality）仅仅意味着“作品由作者独立创作（而非复制自其他作品），并且至少具有某种最低限度的创造性”。[^76] 这种原创主义观念关注特定作品的表达性要素，并考察人类作者在提供提示词方面所扮演角色的分量。

2025 年 1 月 29 日，美国版权局发布了《版权与人工智能报告》（Copyright and Artificial Intelligence Report，下称《版权报告》）的第二部分，聚焦 AI 生成输出的可版权性（copyrightability）问题。[^77] 在这份报告中，版权局得出结论：既有的版权法仍适用于新兴 AI 技术。[^78] 报告为展开分析而收集并考量了公众意见，但最终驳回了“必须修改法律以应对国际竞争”的主张。[^79]

虽然版权局并未明确论及模型蒸馏的合法性，但其当前立场确认：纯由 AI 生成的输出，除非包含充分的人类创作，否则不具备获得版权保护的资格。[^80] 这引出一个重要问题：现行法律对 LLM 的保护缺位，是否正是围绕模型蒸馏之类实践的法律不确定性之根源？如果前沿 LLM 将来获得某种形式的版权保护——无论是针对其结构、输出还是底层训练方法——这是否会改变对蒸馏行为的法律评价？要评估模型蒸馏的法律地位，首先必须了解现今 LLM 享有何种知识产权保护，尤其是涉及其源代码（source code）、模型权重（model weights）与训练数据的保护。[^81] 这也需要考察这些模型是如何被训练的，以及人类的投入或创作在多大程度上参与了其形成。唯有在此基础上，我们才能开始评估模型蒸馏在更宏观的知识产权框架中的位置，以及它是否——或在何种条件下——可能构成侵权。

### A. 现行版权法框架（Existing Copyright Framework）

美国版权局承认，源代码一经固定于有形媒介——例如被写下或以数字方式保存——即受保护。[^82] 在版权法之下，源代码属于文字作品（literary work），保护很可能及于思想的表达，包括代码特定的结构、语法与指令序列。[^83] 然而，版权并不延伸至代码所实现的思想、算法、数据结构、编程语言或功能行为。[^84] 从本质上讲，版权保护的是代码的编写方式，而非它所实现的思想或过程。

要通过侵权之诉证明侵权，必须拥有有效的版权，并证明对受保护要素的复制。[^85] 这通常通过将被控侵权代码与原始源代码进行比对、以识别显著相似（substantial similarity）之处来完成。此类分析往往需要对代码的若干关键方面进行细致审查，包括其结构、架构、变量名、注释，乃至特定的编程模式。确立版权侵权通常需要证据表明：代码的独特表达——即其编写方式——与另一部受版权保护的作品足够相似。

而在 LLM 蒸馏的语境下，法律分析就没那么直截了当了。蒸馏过程并不需要接触教师模型的源代码，而是依赖于对可观察行为的模仿，例如通过 API 查询获得的模型输出。因此，往往不存在对代码的直接复制，被复制的只是功能性回应或决策模式，而这些通常不受版权法保护。将开源代码用于训练，则会引入更多要求，例如特定许可证方面的要求。

由于版权法只保护原创表达，而不保护思想、功能或操作方法，[^86] 经由蒸馏传递的知识与行为通常处于其保护范围之外。这使得 AI 公司除非有明确证据表明源代码或表达性内容遭到直接复制，否则难以主张版权请求。在很大程度上，LLM 中可能受版权保护的要素包括：用于实现该模型的原创源代码，以及训练数据特定的编排与呈现方式（前提是具有足够的创造性，且有待尚未判决的案例确认）。而可以明确断言的是：模型的功能行为、习得的权重、算法，或蒸馏模型模仿而来的输出，不太可能具有可版权性。

#### i. 训练源代码（Training Source Code）

训练源代码是指用于开发和微调 AI 模型的软件指令与算法，包括指导 LLM 训练过程的底层架构、训练脚本、优化流程与数据处理管道。[^87] 如下文将进一步说明的，在未经授权的模型蒸馏情形中，实施蒸馏的一方通常无法接触教师模型的专有源代码。正是由于这种隔绝，教师模型的实际代码库在蒸馏过程中被复制或再现的可能性很低。美国版权法保护软件代码的字面表达（即具体的代码行），但不保护其底层的思想、算法或功能。[^88] 这一原则在 Oracle America 公司诉 Google 案（Oracle America, Inc. v. Google LLC）中得到确认：法院认为，尽管软件代码可以作为文字作品受保护，但方法或结构等功能性要素并不能独立获得版权保护。[^89]

因此，除非源代码本身遭到直接访问或复制，模型蒸馏并不构成传统意义上的软件版权侵权。风险转而在于：蒸馏过程中所复制的输出或行为，是否构成对知识产权的未经授权使用，例如违反使用条款、侵占商业秘密，或对受保护输出的间接复制。

#### ii. 训练数据（Training Data）

模型蒸馏所用的训练数据通常由教师模型生成的输出构成，经收集后再用于训练学生模型。[^90] 在未经授权的蒸馏情形中，这类数据集往往通过反复的 API 查询或大规模的输出采集而建立。[^91] 尽管这些输出可能凝结着教师模型设计与训练中投入的智力劳动，但其作为可版权数据的地位在法律上是模糊的。模型输出——尤其是由预测、补全或生成的回应所构成的内容——更接近事实性或功能性数据，而非表达性作品。[^92] 因此，即使底层模型耗费了巨量资源才产出它们，它们也可能落在保护范围之外。

此外，Feist 出版公司诉 Rural 电话服务公司案（Feist Publications, Inc. v. Rural Telephone Service Co.）确立的法律学说澄清：原始数据或事实汇编不具有可版权性，除非其选择或编排体现了最低限度的创造性。[^93] 将此适用于模型蒸馏，这意味着：虽然输出本身可能不受保护，但由这些输出构成的、经过独特组织的数据集可能符合汇编（compilation）的资格——但前提是有人在数据的选择、排序或分组上行使了独创性。在这一框架下，人类创造了源代码并设计了模型架构，但正如已有的认定所示，这与输出的实际创造相距太远。《版权报告》强烈暗示，设计这些 LLM 的人类要素与输出本身之间的联系过于疏远，因而不能纳入受版权保护的表达。[^94]

然而在实践中，大多数蒸馏数据集是自动生成的，通常是借助随机或系统化的提示词大规模查询教师模型而得。[^95] 此外，LLM 正被设计为通过内部预测任务（自监督，self-supervision）、从 AI 反馈中进行强化学习（Reinforcement Learning from AI Feedback, RLAIF）、自我生成推理、合成数据生成等过程实现自我教学。[^96] 这一过程总体上是机械性的，缺乏汇编版权所要求的创造性裁量。[^97] 因此，即使数据集凝结了可观的努力或投入，在现行版权标准之下也可能得不到法律保护。

其影响是重大的：如果蒸馏中使用的教师模型输出并不构成受保护的内容或汇编，那么用它们来训练学生模型可能并不违反版权法——即使最终得到的学生模型与教师的行为高度相似。这凸显了保护 LLM 商业价值的一大难题：除非合同法或商业秘密法适用，否则模型输出可以被自由采集和复用。

#### iii. 生成模式（Generated Modes）

围绕 LLM 的一个核心法律不确定性是：其各构成要素——原创源代码、转换器这类标准化架构，以及由抓取内容或开源内容构成的庞大数据集——在多大程度上受版权保护。特定的实现代码可能受保护，但底层架构与习得的模型权重可能不受保护，因为它们大概被视为功能性的而非表达性的。使问题更为复杂的是，LLM 常常在公开可得但未经许可的数据上训练，其中包括本身即缺乏版权保护的 AI 生成输出。[^98] 当学生模型从以这类数据训练的教师模型中学习时，创新与复制之间的界线便趋于模糊，给模型开发中的独创性、所有权与可执行性留下了悬而未决的问题。

模型权重与参数代表从训练数据中习得的数值，不作为创造性表达受到保护。它们通常被理解为算法的功能性输出，而非人类创作的内容。[^99] 因此，训练后的模型作为一个整体不能获得版权，因为它主要由抽象思想、算法与事实构成，而这些均处于版权保护范围之外。使问题进一步复杂化的是训练所用数据的性质。LLM 经常在海量数据集上训练，其中包括公开可访问但不一定获得公开许可的内容，例如源自 Common Crawl 的材料——这是一个广泛用于训练最先进模型的大型网络数据集。[^100] 研究表明，该语料库包含未经明确许可而从受版权保护来源抓取的材料。[^101]

这造成了法律图景的混沌。尽管 LLM 复现了从宝贵资源中习得的复杂行为，但其构成要素可能缺乏可执行的版权保护。当学生模型模仿在开放或未经许可数据集上训练的教师模型时，创新与复制之间的区别愈发模糊，给 AI 开发中的独创性、所有权以及知识产权执行的边界留下了悬而未决的问题。
## II. 模型蒸馏是否构成版权侵权？（IS MODEL DISTILLATION COPYRIGHT INFRINGEMENT?）

在现行版权法律框架之下，未经授权的蒸馏不太可能构成版权侵权。更简短地说：如果该模型基于开源模型，那几乎可以肯定不构成。完整地讲，模型蒸馏的目标只是把一个庞大复杂模型的知识转移给一个更小、更高效的模型，这一过程是学生模型从教师的输出中学习——而非直接复制其内部权重或架构。模型蒸馏并不是在复制 LLM 所给出的答案，而是在复制模型回答问题的方式，归根结底是在复制一个过程。

蒸馏过程中的学生模型或许可被视为教师模型的派生物（derivative），但主张版权侵权在法律上颇为复杂。学生模型的架构往往不同，而版权只保护表达性要素——不保护抽象思想、过程或功能。由于 LLM 由数值权重而非表达性代码所定义，学生模型是否含有足以触发版权责任的、与其教师的相似性，仍不明确。

如前所述，与版权侵权最相关的模型蒸馏环节，可能集中于三处：使用相同数据训练学生模型、学生模型对教师模型的模仿，以及为探明教师模型架构而进行的反向提示词工程（reverse prompt engineering, RPE）。

### A. 训练数据的利用（Utilization of Training Data）

有人认为，这个问题在很大程度上取决于尚待法院裁判的案件，例如《纽约时报》诉微软等被告案（New York Times v. Microsoft et al.）。2025 年美国版权局《版权与人工智能报告》重申，版权要求人类创作。[^102] “Zarya of the Dawn”案的裁决进一步确认：对于以提示词生成作品的用户而言，AI 生成的作品不具有可版权性，除非该个体在具体的附加修改中发挥了决定性作用。[^103] AI 只是工具而非作者，这使得大多数 AI 生成内容不具备获得版权的资格。这意味着 OpenAI 将难以对 ChatGPT 的输出主张版权保护，从而削弱其在针对 DeepSeek 将这些输出用于训练一事上的法律地位。而 Feist 案并不能作为本案的准确类比，[^104] 因为 LLM 回答问题的过程并不等同于编排事实——其中涉及某种程度的“批判性思维”，一种超越对事实数据作纯粹机械编排的高阶计算创造力与情境推理。

在微软案中，《纽约时报》主张，LLM 并非仅仅处理事实性信息——它们还在模仿表达，而表达受版权法保护。起诉状强调，LLM 摄取了新闻写作的风格、结构与创造性，有时生成的回应与受版权保护的文章高度相似。[^105] 与检索事实性摘录的传统搜索引擎不同，LLM 合成信息的方式模糊了参考与复制之间的界线。《纽约时报》列举了 ChatGPT 输出改写或几乎复刻其原创文章的实例，并指称这损害了其将新闻变现的能力。[^106]

这一论点十分关键：版权不保护事实，但保护事实被表达的独特方式。通过在受版权保护的材料上训练，LLM 未经许可便内化并再生了表达性要素。《纽约时报》断言，这种做法跨越了法律边界，因为它使 AI 生成的内容得以替代——并可能最终取代——人类创作的新闻作品。[^107] 该诉讼的立场与《纽约时报》在 Tasini 诉《纽约时报》公司案（Tasini v. New York Times Co.）中的立场形成鲜明对照：在那起案件中，与之对抗的正是主张对其数字文章享有版权的自由撰稿人。[^108] 当年，《纽约时报》优先考虑的是技术的可及性，主张严格的版权执法会损害创新；如今，它却要求对其自身作品给予刚性保护以对抗 AI，甚至要求销毁以其内容训练的模型。这种转变暴露出一个更广泛的张力：如何在版权执法与 AI 驱动进步的现实之间取得平衡。

虽然这场诉讼将划定合理使用的边界，以及法院应如何处理模型无意中再现受版权保护材料的情形，但它仍未触及模型蒸馏的根本问题——即大语言模型是如何得出这些答案、又以何种方法生成这些回应的过程。

### B. 模仿教师模型行为（Mimicking Teacher Behavior）

模型蒸馏的核心，是学生模型通过模仿教师模型的行为来学习。这涉及通过接触大量由教师生成的输入—输出对，来复现一个更复杂语言模型的输出、语气、推理模式与风格选择。在版权法中，对行为与表达的模仿触及一个基本原则：版权保护原创的人类表达。法律制度将创造力、独创性与作者身份视为人类独有的特质，不把版权保护延伸至纯算法性或机器生成的输出——近期的美国版权局政策指南再次确认了这一点。[^109] 此外，法院受制定法约束，必须裁定思想、系统或操作方法不受版权法保护。[^110]

然而，这引出一个关键问题：法律上对“行为”的定义，是否过于狭窄地聚焦于人类表达？在 LLM 的语境下，“行为”不仅包括书面输出，还包括经训练而涌现的概率模式、风格决策与决策启发式。这些看似原创，实则是训练所用数据的统计回声——缺乏现行版权框架下获得版权资格所需的独立意图或意识。正如法院与政策机构所澄清的，版权只保护作品中由人类创作的要素。[^111] 在蒸馏中，当学生模型复制教师模型的行为模式时——尤其当该教师模型本身并不生成可版权内容时——该过程很可能落在传统版权保护的边界之外。这使维权变得复杂，因为被复制的对象是行为仿真，而非字面文本。

这一原则使“LLM 习得的行为——它可能映照出风格或功能——本身受保护”之类的主张变得复杂。但随着 AI 系统日益逼近人类式的创造力、生成与受保护表达相似的作品，未来的法律检验标准可能会探讨：LLM 与人类创作的作品须吻合到何种程度，才会触发侵权责任。

### C. 经由逆向工程的（非）直接复制（(In)Direct Copying via Reverse Engineering）

美国版权法只对由人类创作的作品授予版权保护。[^112] 由于 AI 的输出与表达由 AI 而非直接由人类产生，它们不被视为可版权的表达。[^113] 由此推论，任何模仿教师模型的行为、表达、语气等的蒸馏模型都是合法的。模型蒸馏中的版权侵权问题，始于模型的架构或内部机制遭到复制之时。

与模型蒸馏更为接近的类比之一是逆向工程——即通过解构产品来理解其设计、功能或运行方式的过程：从“已知产品”出发，反向推导其实现过程。[^114] 在 AI 语境下，DeepSeek 虽未直接复制 ChatGPT 的内部权重或架构，但它依赖 ChatGPT 生成的输出来训练自己的模型。然而，如前所述，LLM 的输出并不具有可版权性。这就引出一个问题：ChatGPT 中蕴含的底层结构或知识，能否通过系统性查询而被推断或重构？

一个有用的类比是：请一位艺术家回答数百万个关于其如何画出代表作的问题。虽然单个问题都不足以直接复现该画作，但其累积效应或许能让某人在从未见过原作笔触的情况下，重绘出一幅相似的画。这一过程走到某一点时，是否会越过界限、构成未经授权且不合伦理的复制？然而，正如 Lotus Development Corp. 诉 Borland International 案（Lotus Development Corp. v. Borland International）所认定的，操作方法——即某人操作某物的方式——不具有可版权性。[^115] 但计算机命令层级与训练后的 LLM 生成输出的方式并不类似：这一类比忽视了从静态软件工具到自主生成系统的转变。LLM 不依赖固定的菜单或命令结构，而是依托对语言、模式与关联的习得表征来运行。

虽然 LLM 没有可见的静态结构，但其内部知识可以通过交互被推断。逆向工程的理念在于：在不接触原始源代码的情况下，系统性地分析一个系统，以理解、复现或提取其底层结构或功能——事实证明，这是一个更贴切的类比。[^116] 长期以来，逆向工程一直被视为洞悉专有技术的一种合法方法。在商业秘密法之下，只要不存在合同或其他法律上的禁止，对产品进行逆向工程以揭示其秘密通常是允许的。[^117] 而在专利法之下，专利权人对发明享有排他性权利，逆向工程并不能作为侵权指控的抗辩。[^118] 传统上，逆向工程并非版权法中的常见概念。然而，在索尼电脑娱乐公司诉 Connectix 公司案（Sony Computer Entertainment, Inc. v. Connectix Corp.）中，第九巡回上诉法院裁定：如果逆向工程是为接触某一受版权保护的计算机程序所体现的思想与功能要素所必需，且寻求此种接触具有正当目的，则其可构成合理使用。[^119] 此外，在 Atari Games Corp. 诉 Nintendo of America Inc. 案（Atari Games Corp. v. Nintendo of America Inc.）中，Atari 通过欺骗手段获取 10NES 源代码并加以使用的行为不构成合理使用，但其对合法持有的芯片中的 10NES 目标代码进行逆向工程则被允许。[^120] 这一裁判结果的前提在于对代码或芯片的合法持有，并表明合理使用只允许 Atari 为理解而逆向工程代码，却不得为其商业使用而利用代码受商业保护的方面。在 Sega Enterprises 诉 Accolade, Inc. 案（Sega Enterprises v. Accolade, Inc.）中，法院认定被告对原告计算机程序的逆向工程构成合理使用，裁定：在不存在接触其不受保护要素的替代手段时，为正当目的对受版权保护的程序进行反汇编构成合理使用。[^121] 较近的 Lexmark International, Inc. 诉 Static Control Components, Inc. 案（Lexmark International, Inc. v. Static Control Components, Inc.）则支持互操作性（interoperability），遏制了版权法以及《数字千年版权法》（DMCA）的过度扩张。[^122] 法院驳回了 Lexmark 关于 SCC 逆向工程其芯片构成版权侵权的主张。[^123] 该复制是功能性的、最小限度的，且为互操作性所必需。[^124]

这与模型架构有何关联？是否可能对模型架构进行逆向工程？当蒸馏模型试图复现或克隆的不仅是行为、还可能是一个 LLM 中受版权保护的方面时，挑战便出现了。从以往案例中提炼各项考量因素——如合法持有、轻微性使用（de minimis）、功能性目的之必要、互操作性——将有助于分析形形色色的模型蒸馏与“逆向工程”技术是否将构成版权侵权。[^125]

反向提示词工程（reverse prompt engineering, RPE）是通过分析模型输出来推断原始输入的过程。[^126] 它是指“向 LLM 提供期望的输出，并让 AI 生成能够产出该理想结果的最优提示词”。[^127] 其核心思想是利用 LLM 自身的输出去猜测生成该输出的提示词。RPE 把 LLM 当作黑盒，你只能接触到它的文本输出。[^128] 在此，反复进行的提示词操纵，是逆向破解 LLM 结构的有效策略之关键。虽然 RPE 在理论上可能揭示模型行为或提示词结构的某些方面，但要做到彻底复制，就必须挖掘出大量受保护信息——多到足以在法律上构成侵权。现有文献表明，输出探测虽能暴露训练内容的若干要素，却不足以揭示更深层的架构细节，如层数、参数或内部设计。[^129] 被暴露的是模型行为，而非权重或内部构造。这些情形中实际发生的，是模型在模仿行为，而非揭示内部设计。由于生成式 AI 产生的输出通常不被视为具有可版权性，其表达在现行法下通常不受保护，因此仅复制模型行为不太可能构成侵权。然而，这引出一个更深的问题：如果一个模型被模仿得如此精准，以至于其输出的风格、语气与内容几乎完全相同，这是否实际上再造了人类作者或原始模型可能产出的同一表达结果？继而，现行版权框架是否应当修改？[^130]

综观逆向工程与版权法的现状——尤其是轻微性（de minimis）原则的普遍适用，以及不愿把版权保护延伸至 AI 生成输出的历史立场——当今大多数反向提示词工程（RPE）技术很可能落在侵权范围之外。法院一贯认为，附随性或最小限度的复制不构成可诉的侵权。正如一篇论文所指出的，“就任何特定作品而言，复制的程度至多是轻微的（de minimis）”，且模型通常不会以实质方式显著记忆或再现任何特定训练样本。[^131] 因此，通过从有限数量的输出中推断提示词结构或行为模式来运作的 RPE，目前可能被视为一种法律上允许的技术——至少在传统版权分析之下如此。因此，在没有具体证据表明蒸馏过程能够解开并发现架构中受版权保护要素的情况下，这不太可能成为许多前沿 LLM 借以获得保护的一条途径。

### D. 抗辩（Defenses）

API 为理解版权法如何适用于大语言模型的构成要素——尤其是在模型蒸馏的语境下——提供了一个极具说服力的类比。作为软件，API 受版权法保护，但仅以其表达（而非其功能）具有原创性为限。[^132] 这包括其代码的结构、顺序与组织，但不包括底层的思想或操作方法。[^133]

这一法律边界在 Google 诉 Oracle 案（Google LLC v. Oracle America, Inc.）中经受检验：最高法院裁定，Google 复制 Java SE 应用程序编程接口（API）的“声明代码”（declaring code）构成合理使用，因而不侵犯 Oracle 在 Java 上的版权。[^134] 尽管如此，法院认定 Google 在开发 Android 平台时对该代码的使用构成合理使用。[^135] 法院强调了使用的目的与性质，认为其具有转换性（transformative），因为 Google 的实现催生了一个服务不同功能、可互操作的新平台。

这一推理对 LLM 蒸馏有直接的影响。蒸馏模型虽源自更大的教师模型，但通常在规模与复杂度上有所缩减、被改用于新的应用，并剥离了原模型的许多组件。[^136] 正如 Google 的 Android 系统一样，蒸馏模型可被视为一个新的技术平台，这在合理使用分析之下可以支持转换性使用（transformative use）的主张——尤其当学生模型并不在同一市场竞争、或仅仅是复现教师模型的输出时。

如果 OpenAI 以合理使用抗辩来为其训练行为辩护——例如依赖海量公开可得的数据——那么当 DeepSeek 被指控非法蒸馏专有系统的输出时，它同样可以尝试援引合理使用。该抗辩能否成立，取决于 DeepSeek 如何收集其训练数据、最终的模型是否提供新功能或服务于不同目的，以及它是否与原模型构成竞争。然而，如果 DeepSeek 违反了 API 服务条款，或以违反合同法的方式获取输出，其合理使用抗辩将大打折扣。

上诉至第九巡回上诉法院的待决集体诉讼——针对 GitHub、微软与 OpenAI 提起——又增添了复杂性。[^137] 该案质疑使用开源许可代码训练 AI 系统的合法性，并提出一个问题：公开可得的代码是否可以在不遵守许可条款的情况下被自由使用。[^138] 原告主张，在不遵守署名或再分发义务的情况下以这类代码训练模型，违反了开源许可的条件。[^139] 如果原告胜诉，该诉讼可能要求开发者审计其训练集、取得许可证或支付版税，从而动摇“公开可得的内容即可自动用于 AI 训练”的假设。

## III. 针对模型蒸馏的替代性保护（ALTERNATIVE PROTECTIONS AGAINST MODEL DISTILLATION）

虽然版权常被视为最直接的保护形式，但它既非唯一、也未必是最有效的保护。更强、更明确的保障可以通过专利保护来实现，或通过策略性地实施规范大语言模型访问与交互的详细使用条款（Terms of Use）来实现。这些机制可以帮助前沿 AI 开发者防止关键模型特性与功能遭到未经授权的复制。

### A. 专利（Patents）

专利可为 AI 创新提供另一层保护，但伴随显著的复杂性。与 AI 相关专利的法律框架仍在演变之中，法院与专利局仍在苦苦权衡：由 AI 生成或辅助完成的发明——尤其是机器学习技术领域的发明——是否满足专利适格性（patent eligibility）标准。如果 AI 专利变得更加普遍，业界可能面临类似智能手机专利战争（Smartphone Patent Wars）的诉讼浪潮——科技公司曾在那样的战争中彼此激烈起诉，以主张知识产权。这样的局面非但不会鼓励创新，反而可能通过制造法律不确定性、抬高新兴开发者的准入成本而扼杀进步。

### B. 使用条款（Terms of Use）

使用条款协议，也称服务条款（Terms of Service）或可接受使用政策（Acceptable Use Policies），是规定用户与第三方如何与 AI 模型或平台交互的合同义务。[^140] 与依赖制定法的专利或商业秘密不同，使用条款通过合同协议来执行，这使其成为 AI 公司手中灵活而有力的工具。[^141] AI 开发者可以利用使用条款限制其模型的使用方式，确保模型不被以损害其商业利益的方式利用。[^142] 公司可以禁止用户大量收集 AI 生成的文本、图像或其他输出来训练竞争性 AI 模型。OpenAI 的使用条款明确声明，用户不得为构建数据集而抓取或提取 ChatGPT 的输出。[^143] 这些协议还可包含禁止反向工程条款，防止用户通过分析模型行为、结构或决策过程来再造一个类似的 AI 系统。一些公司的条款中包含禁止反编译、反汇编或其他形式的 AI 模型逆向工程的内容。[^144] 此类“禁止反向工程”条款曾获得法院支持，如 Bowers 诉 Baystate Technologies, Inc. 案（Bowers v. Baystate Technologies, Inc.）所示。[^145]

除限制反向工程外，使用条款还可以通过为第三方开发者将 AI 模型集成到其平台的方式设定限制，来控制 API 的使用。[^146] 一家提供 AI 生成艺术工具的公司，可以禁止 API 用户把该技术嵌入未经授权的平台。伦理与合规标准也常被纳入这些协议，界定 AI 模型的使用方式，防止违反伦理标准、法律要求或公司政策的应用。[^147] 例如，AI 医疗诊断工具的使用条款可能禁止获得批准的医务人员之外的人使用。一些公司还利用这些协议执行货币化与许可限制，防止用户在未获得适当许可的情况下转售或再分发 AI 生成内容。一些 AI 内容生成器允许个人使用，但要求企业购买额外的商业许可。

虽然使用条款（Terms of Use，“TOU”）仍是规范数字服务访问、保护专有模型的基础法律机制，但其可执行性取决于具体情境，且在缺乏配套保障措施时作用有限。正如 Van Buren 诉合众国案（Van Buren v. United States）所澄清的，违反使用条款本身并不构成《计算机欺诈与滥用法》（Computer Fraud and Abuse Act）意义上的未经授权访问；该制定法针对的是传统黑客行为，而非内部滥用或违约。[^148] 类似地，hiQ Labs, Inc. 诉 LinkedIn Corp. 案（hiQ Labs, Inc. v. LinkedIn Corp.）认定：在数据公开可得的情况下，仅有使用条款可能无法阻止抓取，除非辅之以实质性的技术屏障或明确的合同约定。[^149] 然而，Register.com, Inc. 诉 Verio, Inc. 案（Register.com, Inc. v. Verio, Inc.）则表明：当用户在已知条款的情况下反复与平台交互时，使用条款可以形成可执行的合同。[^150] 这些案例共同表明：使用条款虽是有力的合同工具，但其威慑与救济效力，最好在明确的同意机制、合同相对性以及技术限制的支撑下方能实现。随着法律图景与 AI 及数据密集型技术同步演进，寻求防止未经授权模型蒸馏或数据提取的平台，必须把使用条款视为基线，而非单独的盾牌。

尽管使用条款提供了强有力的保护层，但其执行面临挑战。不同国家的用户可能受合同条款不同法律解释的约束。公司必须建立追踪未经授权使用的机制，而对开源模型或广泛分发的 AI 工具而言，这可能十分困难。执行使用条款往往需要法律行动，费用高昂且旷日持久。强化使用条款的一条可能路径是全行业协作。如果领先的 AI 公司制定标准化的合同条款，不良行为者将更难利用 AI 系统，同时确保合理使用与创新不致受阻。
## IV. 变革的可能性与开源需求的兴起（POTENTIAL FOR CHANGE AND THE RISE IN DEMAND FOR OPEN-SOURCING）

### A. 版权框架是否应当修改？（Should the Copyright Framework be Altered?）

人工智能作为创作工具的兴起，促使法律学者、技术专家与政策制定者重新审视一个根本问题：版权保护是否应当演进，以反映非人类参与者在创作过程中的角色。这场辩论的核心是作者身份（authorship）概念——依据美国版权法谁有资格成为“作者”——以及 AI 作为表达性作品的生成者，是否应被承认为作者。《版权法》规定，版权保护及于“固定于任何有形表达媒介中的原创作者作品”。[^151] 尽管该制定法并未明确要求作者必须是人类，但美国版权局与联邦法院一贯将其解释为包含此要求。[^152] 从教义上看，重点在于独创性——但这引出一个更深的问题：“独创”究竟意味着什么？独创性是人类固有的特质，还是也可能产生于 AI 模型的计算过程？

作家 William Plomer 曾言：创造力在于把互不相干的思想组合为新颖而有意义之构型的能力。[^153] 如果此言不虚，那么独创性就不是凭空发明思想，而是以别出心裁的方式重构既有知识。就此而言，擅长混合与情境化数据的 AI，可以说符合这一定义。虽然 AI 系统仅以历史数据训练、通过算法预测运作，但这恰恰模拟了人类生成知识的方式——把过往经验与环境刺激重新组合。因此，人类创造力与机器创造力之间的区别，也许只是程度之别，而非本质之别。

这种张力在认知科学与计算语言学中同样有所映照。例如，麻省理工学院计算机科学与人工智能实验室 2024 年的一项研究表明：一个在机器人控制指令上训练的 LLM，尽管从未被明确展示底层机制，却发展出了对模拟环境的内部表征。[^154] 借助“探测”（probing）方法，研究者得出结论：该模型仅凭语言便生成了有意义的概念结构。[^155] 如果语言模型能够形成物理系统的内部对应物，这就挑战了关于何为“理解”或“意图”的传统假设。

尽管如此，AI 模型仍然需要人类的指引。它们并非在真空中生成创意作品，而是回应用户精心设计的输入——提示词。就此而言，AI 发挥着工具的作用，尽管是一个高度先进且半自主的工具。法院与监管机构也持这种观点。在 2023 年的政策指南中，美国版权局澄清：只有当涉及充分的人类创作时，AI 生成的作品才可能获得保护。[^156] 法院同样认定，人类必须对作品行使“创作性控制”。[^157]

从规范角度看，版权法必须围绕能够感受损害并寻求法律救济的实体来构建。AI 不具备人格（personhood）、道德能动性或诉讼资格（standing）。即使某个 AI 系统产出了全新的东西，由此产生的任何侵权所伤害的，也是该系统背后的人类开发者、用户或利益相关者——而非机器本身。将人类保持为作者身份的核心单元，确保了问责性、一致性以及对创意经济的保护。

在通用人工智能（artificial general intelligence, AGI）——能够自主决策、具有创作意图并能为自身主张权益——出现之前，美国版权法下“作者身份”的定义不太可能改变。也不应当改变。如前所述，现行判例支持这样一种理念：版权应继续以有意义的人类参与为条件。这一路径确保法律继续服务于其首要目的：鼓励人类创造，并在这种创造遭到滥用时提供救济。

### B. 开源的呼吁（The Call for Open-Sourcing）

随着当今这场奔向通用人工智能（AGI）的“太空竞赛”提速，一个根本性的问题浮现：专有式开发是通往安全且公平的 AGI 的正途，还是阻碍进步、固化垄断？OpenAI 曾是开源研究的主要倡导者，如今却转向封闭模式，理由是安全顾虑、竞争与滥用风险。但这一转变招致了 AI 社区内外的审视。

在 2024 年一次坦率的表态中，OpenAI 首席执行官 Sam Altman 承认，就 AI 开发中的开放性而言，公司可能“站在了历史的错误一边”。[^158] 大约同一时期，DeepSeek 创始人梁文锋（Liang）自中国发出了直接挑战，他宣称：“面对颠覆性技术，闭源筑就的护城河是暂时的。即使是 OpenAI 的闭源路线，也无法阻止他人追赶。”[^159] 这些言论凸显了一个更大的张力：对 LLM 的专有控制，会促成负责任的规模化，还是会扼杀创新、造成 AI 开发中的全球不对称？更关键的是：如果无论如何保密，大家终将追平，那么知识产权排他性究竟还有什么用？

从法律视角看，让 AI 系统保持闭源可能强化知识产权主张。版权、商业秘密与合同法（通过使用条款）在访问受到严格管控时更易于执行。相反，开源模型招致审视、复用，乃至未经授权的商业化。但开源行为也确立了透明度的基线，能够促进可复现性、推动科学发现，并让强大的 AI 系统走向普惠。

一些学者认为，开放模型可能削弱单个企业的知识产权地位，但与此同时增强公众的集体知识。正如制药业的开放科学运动或学术联盟早期开发的网络协议那样，开源前沿模型可以拉平竞争环境——使 AGI 开发成为一项全球性的科学追求，而非企业间的军备竞赛。尽管如此，开源也有代价。它可能限制企业就模型蒸馏主张权利的能力，令专利策略复杂化，并暴露自身弱点。但它也可以划清哪些创新真正新颖、哪些属于派生，以及在 AI 开发日益协作化、去中心化之际，法律规范应当如何演进。

OpenAI 是否会以潜在的逆向工程或未经授权训练为由，起诉 DeepSeek 之类的竞争对手，尚待观察。但也许更重要的问题不是 OpenAI 能否起诉——而是它是否应当起诉。在一个创新与模仿的界线日益稀薄的世界里，AI 社区或许需要重新思考：传统的知识产权制度，是否足以应对 AGI 时代的独特需求。

## 结论（CONCLUSION）

模型蒸馏代表着人工智能演进中的一个关键拐点——创新在此与过时的法律框架相撞。虽然蒸馏使较小的实验室得以复制前沿模型的性能，但这一过程很少涉及对受版权保护内容的直接复制；相反，它踏入的是美国版权法并未明确保护的地带。除非未来的立法扩展受保护表达的定义，把模型行为、习得的权重或结构化输出纳入其中，否则版权侵权主张将面临巨大的障碍。这种法律上的不确定性指向两种可能的未来：其一，AI 创新被过度扩张的知识产权执法所扼杀；其二，开源与协作推动全球迈向通用人工智能。如果法律继续把人类创作与表达置于首位，那么专有式 AI 开发者将不得不更倚重合同、专利与平台控制，而非传统版权。归根结底，随着模仿与创造的界线持续模糊，问题或许不再在于 AI 生成的输出是否值得保护——而在于法律制度本身是否必须演进，以满足一个机器驱动时代的需求。

## 注释（FOOTNOTES）

[^1]: Zhiwei Yao, Yang Xu, Hongli Xu, Yunming Liao & Zuan Xie, Efficient Deployment of Large Language Models on Resource-constrained Devices 1–2, ARXIV（2025年1月5日），https://arxiv.org/pdf/2501.02438。
[^2]: Rajdeep Borgohain, Distilling Large Language Models, INFERLESS（2025年3月31日），https://www.inferless.com/learn/distilling-large-language-models。
[^3]: Dave Bergmann, What is Knowledge Distillation?, IBM（2024年4月16日），https://www.ibm.com/think/topics/knowledge-distillation。
[^4]: 同前注。
[^5]: Model Distillation Making AI Models Efficient, DEEPINFRA（2025年4月10日），https://deep-infra.com/blog/model-distillation?。
[^6]: David M. Levine, Rudraksh Tuwani, Benjamin Kompa, Amita Varma, Samuel G. Finlayson, Ateev Mehrotra & Andrew Beam, The Diagnostic and Triage Accuracy of the GPT-3 Artificial Intelligence Model（PubMed Central, PMC9915829，2023年2月1日），https://pmc.ncbi.nlm.nih.gov/articles/PMC9915829/；Implementing Web Scraping in Python with Scrapy, GEEKS FOR GEEKS（2025年8月23日），https://www.geeksforgeeks.org/python/implementing-web-scraping-python-scrapy/；Octoparse Beginner's Guide, OCTOPARSE, https://dataservice.octoparse.com/octoparse-hello-world（最后访问于2025年10月21日）。
[^7]: Cole Stryker, What are Large Language Models (LLMs)?, IBM（2025年9月10日），https://www.ibm.com/think/topics/large-language-models?。
[^8]: 参见 Anup Shirgaonkar, Nikhil Pandey, Nazmiye Ceren Abay, Tolga Aktas & Vijay Aski, Knowledge Distillation Using Frontier Open-Source LLMs: Generalizability and the Role of Synthetic Data 2, ARXIV（2024年10月24日），https://arxiv.org/pdf/2410.18588。
[^9]: 起诉状，Complaint, New York Times Co. v. Microsoft Corp., No. 1:23-cv-11195 (S.D.N.Y. Dec. 27, 2023)（指控 OpenAI 与微软未经许可使用数百万篇受版权保护的《纽约时报》文章训练其 AI 模型（包括 ChatGPT），导致输出与《纽约时报》内容高度相似或构成复制）。
[^10]: 另参见 Memorandum Opinion—Document #547, Thomson Reuters Enter. Ctr. GmbH et al. v. ROSS Intel. Inc., No. 1:2020-cv-00613 (D. Del. 2023)（法院认定，使用受版权保护的法律判决摘引（headnotes）训练 AI 模型不构成合理使用，凸显了为训练数据取得适当许可的重要性）。
[^11]: Cameron R. Wolfe, Scaling Laws for LLMs: From GPT-3 to o3, DEEP (LEARNING) FOCUS（2025年1月6日），https://cameronrwolfe.substack.com/p/llm-scaling-laws。
[^12]: 另参见 Falcon, RefinedWeb Dataset, Common Crawl, The Pile；BloombergGPT。
[^13]: Sumit Singh, Data Collection and Preprocessing for Large Language Models, LABELLERR（2024年9月27日），https://www.labellerr.com/blog/data-collection-and-preprocessing-for-large-language-models。
[^14]: Dave Salvator, Explaining Tokens–the Language and Currency of AI, NVIDIA（2025年3月17日），https://blogs.nvidia.com/blog/ai-tokens-explained/。
[^15]: 同前注。
[^16]: 参见 Ayushman Pranav, Exploring Subword Tokenization in Natural Language Processing with Python, MEDIUM（2024年5月7日），https://medium.com/@AyushmanPranav/exploring-sub-word-tokenization-in-natural-language-processing-with-python-adcf027deb4e。
[^17]: Salvator，前注14。
[^18]: CryptoGPTo, Introduction to Large Language Models and the Transformer Architecture, MEDIUM（2023年3月8日），https://rpradeepmenon.medium.com/introduction-to-large-language-models-and-the-transformer-architecture-534408ed7e61。
[^19]: Sella Nevo, Dan Lahav, Ajay Karpur, Yogev Bar-on, Henry Alexander Bradley & Jeff Alstott, Securing AI Model Weights 3 (2024)。
[^20]: 总体参见 Jenny Quang, Does Training AI Violate Copyright Law?, 36 BERKELEY TECH. L.J. 1407, 1410–12 (2023)。
[^21]: Token Licensing, IBM, https://www.ibm.com/docs/en/mqa/7.0.0?topic=installation-token-licensing（最后更新于2021年8月3日）。
[^22]: Tokens and Tokenization in Large Language Models in Python, GITHUB（2024年9月11日），https://github.com/explosion/spaCy?tab=MIT-1-ov-file#readme。
[^23]: 同前注。
[^24]: 同前注。
[^25]: 同前注。
[^26]: 参见，如 Should Your AI Agent Use Token-Based or Subscription Pricing?, MONETIZELY（2025年7月21日），https://www.getmonetizely.com/articles/should-your-ai-agent-use-token-based-or-subscription-pricing?
[^27]: What is LLM (Large Language Model)?, AMAZON WEB SERVICES, https://aws.amazon.com/what-is/large-language-model/（最后访问于2025年10月21日）。
[^28]: CryptoGPTo，前注18。
[^29]: Dave Bergmann & Cole Stryker, What is an Attention Mechanism?, IBM（2024年12月4日），https://www.ibm.com/think/topics/attention-mechanism。
[^30]: 参见 Rob Ashmore, Radu Calinescu, & Colin Paterson, Assuring the Learning Lifecycle: Desiderata, Methods, and Challenges, ARXIV（2019年5月），https://arxiv.org/pdf/1905.04223。
[^31]: 同前注。
[^32]: 同前注。
[^33]: 同前注。
[^34]: Dave Bergmann, What is Knowledge Distillation?, INT'L BUS. MACHINES, https://www.ibm.com/think/topics/knowledge-distillation（最后访问于2025年10月21日）。
[^35]: Luyang Fang et al., Knowledge Distillation and Dataset Distillation of Large Language Models: Emerging Trends, Challenges, and Future Directions 5–6, ARXIV（2025年4月20日），https://arxiv.org/abs/2504.14772。
[^36]: 同前注；另参见 Jie Zhang, Chen Chen, & Lingjuan Lyu, IDEAL: Query-Efficient Data-Free Learning from Black-box Models, ARXIV（2023年8月），https://arxiv.org/abs/2205.11158。
[^37]: Fang et al.，前注35。
[^38]: Zhang et al.，前注36。
[^39]: Zhang et al.，前注36。
[^40]: Mehul Gupta, What are DeepSeek-R1 Distilled Models?, MEDIUM（2025年1月21日），https://medium.com/data-science-in-your-pocket/what-are-deepseek-r1-distilled-models-329629968d5d。
[^41]: 参见 Yijun Tian et al., Knowledge Distillation on Graphs: A Survey, 57 ASSOCIATION FOR COMPUTING MACHINERY COMPUTING SURVEYS 8（2025年3月5日），https://dl.acm.org/doi/10.1145/3711121。
[^42]: Saptarshi Mandal, Xiaojun Lin, & R. Srikant, A Theoretical Analysis of Soft-Label vs. Hard-Label Training in Neural Networks, ARXIV（2024年12月12日），https://arxiv.org/abs/2412.09579（研究发现，就准确率而言，软标签训练始终优于硬标签训练）。
[^43]: Valentina Alonso, From Teacher to Student: Model Distillation for Cost-Effective LLM Deployment, MARVIK（2025年1月28日），https://blog.marvik.ai/2025/01/28/from-teacher-to-student-model-distillation-for-cost-effective-llm-deployment/。
[^44]: 参见同前注。
[^45]: 参见同前注。
[^46]: Himanshu Bamoria, Unlocking the Power of Large Language Models: A Deep Dive into LLM Distillation, MEDIUM（2024年9月11日），https://medium.com/athina-ai/unlocking-the-power-of-large-language-models-a-deep-dive-into-llm-distillation-59f89828cae5。
[^47]: Subhash Saravanan, Knowledge Distillation: Bridging the Gap Between Large Models and Practical Applications, MEDIUM（2025年2月1日），https://medium.com/@subhashve4/how-deepseek-r1s-distilled-models-differ-from-the-real-thing-a-guide-to-knowledge-distillation-0d3d46dd8a9e。
[^48]: 同前注。
[^49]: 同前注。
[^50]: LLMs: Fine-Tuning, Distillation, and Prompt Engineering, GOOGLE FOR DEVS.（2025年8月25日），https://developers.google.com/machine-learning/crash-course/llm/tuning。
[^51]: 参见 Saravanan，前注47。
[^52]: 同前注。
[^53]: Robert Hulse, Tyler G. Newby, Stuart P. Meyer, & Frederick Tsang, DeepSeek, Model Distillation, and the Future of AI IP Protection, FENWICK & WEST LLP（2025年2月3日），https://www.fenwick.com/insights/publications/deepseek-model-distillation-and-the-future-of-ai-ip-protection。
[^54]: 参见 Alistair Barr, AI Hypocrisy: OpenAI, Google and Anthropic Won't Let Their Data Be Used to Train Other AI Models, but They Use Everyone Else's Content, BUS. INSIDER（2023年6月2日），https://www.businessinsider.com/openai-google-anthropic-ai-training-models-content-data-use-2023-6?utm；另参见 Commercial Terms of Service, ANTHROPIC（2025年6月17日），https://www.anthropic.com/legal/commercial-terms（描述 Anthropic 服务的使用限制）。
[^55]: 参见同前注。
[^56]: 总体参见 DeepSeek-AI et al., DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning, ARXIV（2025年1月22日），https://arxiv.org/pdf/2501.12948（概述 DeepSeek-R1 如何是对 DeepSeek-R1-Zero 的改进）。
[^57]: 参见 Kelly Ng et al., DeepSeek: The Chinese AI App That Has the World Talking, BBC（2025年2月4日），https://www.bbc.com/news/articles/c5yv5976z9po。
[^58]: 参见 CNBC, How China's New AI Model DeepSeek is Threatening U.S. Dominance, YOUTUBE（2025年1月24日），https://www.youtube.com/watch?v=WEBiebbeNCA。
[^59]: 参见 Jess Weatherbed, OpenAI Has Evidence that its Models Helped Train China's DeepSeek, THE VERGE（2025年1月29日），https://www.theverge.com/news/601195/openai-evidence-deepseek-distillation-ai-data。
[^60]: Will Douglas Heaven, How DeepSeek ripped up the AI playbook—and why everyone's going to follow its lead, MIT TECH. REV.（2025年1月31日），https://www.technologyreview.com/2025/01/31/1110740/how-deepseek-ripped-up-the-ai-playbook-and-why-everyones-going-to-follow-it/。
[^61]: 同前注。
[^62]: 参见 Jasmine Wu & Deirdre Bosa, How DeepSeek Used Distillation to Train its Artificial Intelligence Model, and What it Means for Companies Such as OpenAI, CNBC（2025年2月21日），https://www.cnbc.com/2025/02/21/deepseek-trained-ai-model-using-distillation-now-a-disruptive-force.html。
[^63]: 同前注。
[^64]: Heaven，前注60（“为作最后一番打磨，DeepSeek 以人们提供的少量示例回应数据集为强化学习过程播种。”）。
[^65]: Heaven，前注60。
[^66]: Mark Sullivan, $100B OpenAI investment shows Nvidia's enduring leverage in AI, FAST COMPANY（2025年9月25日），https://www.fastcompany.com/91410528/100-billion-open-ai-nvidia-data-center-energy。
[^67]: Wu & Bosa，前注62。
[^68]: Ben Fritz, DeepSeek's AI Learned from ChatGPT, Trump's AI Czar Says, WALL ST. J.（2025年1月28日），https://www.wsj.com/livecoverage/stock-market-today-dow-sp500-nasdaq-live-01-28-2025/card/deepseek-s-ai-learned-from-chatgpt-trump-s-ai-czar-says。
[^69]: 同前注。
[^70]: University of Bath, Study Warns API Restrictions by Social Media Platforms Threaten Research, LAB MANAGER（2023年11月3日），https://www.labmanager.com/study-warns-api-restrictions-by-social-media-platforms-threaten-research-31235；另参见 J. Simpson, AI's Glaring Problem: API Security, NORDIC APIS（2024年7月11日），https://nordicapis.com/ais-glaring-problem-api-security/（“LLM 的流行催生了一种全新的安全威胁，即提示词注入。OWASP 将提示词注入定义为通过精心构造的输入操纵 LLM，可能导致未经授权的访问、数据泄露与决策遭到破坏。”）。
[^71]: Eliza Strickland, Google Is Now Watermarking Its AI-Generated Text > But the DeepMind technology isn't yet a practical solution for everyone, IEEE SPECTRUM（2024年10月24日），https://spectrum.ieee.org/watermark。
[^72]: 参见 Matt Blaszczyk, Geoffrey McGovern, & Karlyn D. Stanley, Artificial Intelligence Impacts on Copyright Law, RAND CORP.（2024年11月20日），https://www.rand.org/pubs/perspectives/PEA3243-1.html。
[^73]: 参见同前注。
[^74]: 例如参见 Thaler v. Perlmutter, 130 F.4th 1039 (D.C. Cir. 2025)；另参见 Zarya of the Dawn Letter, U.S. COPYRIGHT OFF.（2023年2月21日），https://www.copyright.gov/docs/zarya-of-the-dawn.pdf（美国版权局发出的信函，解释因漫画中包含 AI 生成图像而部分撤销其版权）；Matt Blaszczyk, Impossibility of Emergent Works' Protection in U.S. and EU Copyright Law, 25 N.C. J.L. & TECH. 1 (2023)。
[^75]: Adrian F. Vallens, Farrah Vasquez, & Nicolas A. Jampol, Appreciable or De Minimis: That Is the AI Question, DAVIS WRIGHT TREMAINE LLP（2023年12月5日），https://www.dwt.com/blogs/artificial-intelligence-law-advisor/2023/12/copyright-appreciable-de-minimis-ai-generated-work。
[^76]: Feist Publ'ns, Inc. v. Rural Tel. Serv. Co., 499 U.S. 340, 345 (1991)。
[^77]: Copyright Office Releases Part 2 of Artificial Intelligence Report–Issue No. 1060, U.S. COPYRIGHT OFFICE（2025年1月29日），https://www.copyright.gov/newsnet/2025/1060.html。
[^78]: 参见 U.S. COPYRIGHT OFF., COPYRIGHT AND ARTIFICIAL INTELLIGENCE PART 2: COPYRIGHTABILITY（2025年1月）。
[^79]: 同前注。
[^80]: 同前注。
[^81]: 例如参见 Ian Goodfellow, Yoshua Bengio & Aaron Courville, Deep Learning (MIT Press 2016)（描述模型权重）。
[^82]: Circular 61: Copyright Registration of Computer Programs, U.S. COPYRIGHT OFF.（2021年3月修订），https://www.copyright.gov/circs/circ61.pdf。
[^83]: Johnson Controls, Inc. v. Phoenix Control Systems, Inc., 886 F.2d 1173, 1176 (1989)。
[^84]: 参见 17 U.S.C. § 102(b) (2023)；另参见 What Does Copyright Protect?, U.S. COPYRIGHT OFF., https://www.copyright.gov/help/faq/faq-protect.html。
[^85]: 参见 17 U.S.C. § 411 (2023)。
[^86]: 参见 U.S. COPYRIGHT OFF.，前注78。
[^87]: Matus Tomlein & Adam Roche, Data Pipeline Architecture for AI: Why Traditional Approaches Fall Short, SNOWPLOW（2025年4月11日），https://snowplow.io/blog/data-pipeline-architecture-for-ai-traditional-approaches。
[^88]: 17 U.S.C. § 102(b)。另参见 Google LLC v. Oracle Am., Inc. 593 U.S. 1, 23 (2021)。
[^89]: 参见 Oracle Am., Inc. v. Google LCC, 886 F.3d 1179, 1204–05, 1210–11 (Fed. Cir. 2018)（描述美国联邦巡回上诉法院如何认定 Oracle 的单点登录（SSO）软件可受版权保护，以及如何接受 Google 提出的以“操作方法”判断可版权性的框架，但最终驳回了 Google 专门针对 Oracle 该 SSO 的论点）。
[^90]: Somin Wadha et al., Who Taught You That? Tracing Teachers in Model Distillation, ARXIV（2025年1月5日），https://arxiv.org/pdf/2501.02438。
[^91]: 同前注。
[^92]: 参见 U.S. COPYRIGHT OFF.，前注78。
[^93]: 参见 Feist Publ'ns Inc. v. Rural Tel. Serv. Co., 499 U.S. 340, 347–48 (1991)。
[^94]: 参见 U.S. COPYRIGHT OFF.，前注78。
[^95]: Haziqa Sajid, Knowledge Distillation: Transferring Knowledge from Large, Computationally Expensive LLMs to Smaller Ones Without Sacrificing Validity, ZILLIZ（2024年11月11日），https://zilliz.com/learn/knowledge-distillation-from-large-language-models-deep-dive。
[^96]: 参见 Jeremy Curuksu, Fine-Tune Large Language Models with Reinforcement Learning from Human or AI Feedback, AMAZON WEB SERVS., INC.（2025年4月4日），https://aws.amazon.com/blogs/machine-learning/fine-tune-large-language-models-with-reinforcement-learning-from-human-or-ai-feedback/。
[^97]: Copyright in Derivative Works and Compilations, U.S. COPYRIGHT OFF.（2020年7月修订），https://www.copyright.gov/circs/circ14.pdf。
[^98]: Katherine Klosek & Marjory S. Blumenthal, Training Generative AI Models on Copyrighted Works Is Fair Use, ASS'N OF RSCH. LIBRARIES（2024年1月23日），https://www.arl.org/blog/training-generative-ai-models-on-copyrighted-works-is-fair-use/。
[^99]: Lisa T. Oratz et al., Copyright Office Stakes Out Position on Use of Works for AI Training, PERKINS COIE（2025年6月9日），https://perkinscoie.com/insights/update/copyright-office-stakes-out-position-use-works-ai-training。
[^100]: Michael Perelkiewicz & Rafal Poswiata, A Review of the Challenges with Massive Web-mined Corpora Used in Large Language Models Pre-Training, ARXIV（2024年7月10日），https://arxiv.org/html/2407.07630v1。
[^101]: Kali Hays & Alistair Barr, The New York Times got its content removed from one of the biggest AI training datasets. Here's how it did it., BUS. INSIDER（2023年11月8日），https://www.businessinsider.com/new-york-times-content-removed-common-crawl-ai-training-dataset-2023-11。
[^102]: 参见 U.S. COPYRIGHT OFF.，前注78，第7–8页；另参见 Naruto v. Slater, 888 F.3d 418, 420 (9th Cir. 2018)（该报告援引的案件之一，重申人类创作的必要性）。
[^103]: 参见 U.S. COPYRIGHT OFF.，前注78（“[美国版权]局将登记包含本来不受保护、但经人类作者编辑、修改或以其他方式修订之材料的作品，但前提是修改后的新作品本身包含足以获得版权保护的‘充分数量的原创创作’。”）；另参见 Thaler v. Perlmutter, 130 F.4th 1039, 1051 (D.C. Cir. 2025)。
[^104]: 参见 Feist Publ'ns., Inc., 499 U.S. at 344。
[^105]: 参见前注9所引起诉状；另参见 Bobby Allyn, 'The New York Times' takes OpenAI to Court. ChatGPT's Future Could be on the Line, NPR（2025年1月14日），https://www.npr.org/2025/01/14/nx-s1-5258952/new-york-times-openai-microsoft。
[^106]: 同前注。
[^107]: 参见同前注（在法庭文件中，Ian Crosby 写道，OpenAI 非法使用《纽约时报》的作品来创建与之竞争的人工智能产品，威胁到《纽约时报》提供该服务的能力。此外，Crosby 称这是“substitional”（原文如此））。
[^108]: 参见 Tasini v. New York Times Co., 206 F.3d 161 (2d Cir. 2000), aff'd, 533 U.S. 483 (2001)。
[^109]: 参见 Thaler v. Perlmutter, 130 F.4th 1039, 1043 (D.C. Cir. 2025)；另参见 Naruto v. Slater, 888 F.3d. 418 (9th Cir. 2018)。
[^110]: 17 U.S.C. § 102(b)。
[^111]: U.S. COPYRIGHT OFF., COPYRIGHT AND ARTIFICIAL INTELLIGENCE PART 2: COPYRIGHTABILITY 18（2025年1月）；参见 U.S. COPYRIGHT OFF.，前注78，第iii页。
[^112]: 参见 Naruto v. Slater, 888 F.3d 418, 420 (9th Cir. 2018)。
[^113]: 参见同前注，第19页（“理论上，AI 系统有朝一日可能使用户能够对其表达在输出中的呈现方式施加足够多的控制，以至于系统的贡献将变得机械而流于程式。但关于当今 AI 系统运行方式的证据表明，目前情况并非如此。提示词似乎不足以决定所产生的表达性要素，也不足以控制系统如何将其转化为输出。”）。
[^114]: Kewanee Oil Co. v. Bicron Corp., 416 U.S. 470, 476 (1974)。
[^115]: Lotus Dev. Corp. v. Borland Int'l, Inc., 49 F.3d 807, 815 (1st Cir. 1995)。
[^116]: William Fleshman & Benjamin Van Durme, RE-Adapt: Reverse Engineered Adaptation of Large Language Models 1, ARXIV（2024年5月23日），https://arxiv.org/abs/2405.15007v1。
[^117]: Kewanee Oil Co., 416 U.S. at 490。
[^118]: 参见同前注。
[^119]: Sony Comput. Ent., Inc. v. Connectix Corp., 203 F.3d 596, 603–04 (9th Cir. 2000)。
[^120]: Atari Games Corp. v. Nintendo of Am. Inc., 975 F.2d 832, 843–44 (Fed. Cir. 1992)。
[^121]: Sega Enter. Ltd. v. Accolade Inc., 977 F.2d 1510, 1518 (9th Cir. 1992)。
[^122]: 参见 Lexmark Int'l, Inc. v. Static Control Components, Inc., 387 F.3d 522, 549, 551 (6th Cir. 2004)。
[^123]: 同前注，第550–51页。
[^124]: 参见同前注，第545–551页。
[^125]: 参见 Sega, 977 F.2d 1510 (9th Cir. 1992)（合法持有）；Ringgold v. Black Entertainment Television, 126 F.3d 70 (2d Cir. 1997)（轻微性使用）；Lexmark, 387 F.3d 522 (6th Cir. 2004)（互操作性）。
[^126]: 参见 Serhii Uspenskyi, Comprehensive Guide to Reverse Prompt Engineering – All You Need to Know, SPRINGS（2024年9月19日），https://springsapps.com/knowledge/comprehensive-guide-to-reverse-prompt-engineering—all-you-need-to-know。
[^127]: Hanqing Li & Diego Klabjan, Reverse Prompt Engineering, ARXIV（2024年11月11日），https://arxiv.org/html/2411.06729v1。
[^128]: 同前注。
[^129]: Nicolas Carlini et al., Extracting Data from Large Language Models 1–3, ARXIV（2021年6月15日），https://arxiv.org/pdf/2012.07805。
[^130]: 参见下文第 IV.A 节。
[^131]: Carlini et al.，前注129，第1页（转引 Kit Walsh, USPTO Request for Comments on Intellectual Property Protection for Artificial Intelligence Innovation – Public Comment by the Electronic Frontier Foundation, U.S. PAT. & TRADEMARK OFF.（2020年1月10日），https://www.uspto.gov/sites/default/files/documents/Electronic%20Frontier%20Foundation_RFC-84-FR-58141.PDF。）。
[^132]: Peter S. Menell, Rise of the API Copyright Dead?: An Updated Epitaph for Copyright Protection of Network and Functional Features of Computer Software, 10 HARV. J.L. & TECH. 305 (2018)。
[^133]: 17 U.S.C. § 102(b)。
[^134]: Google LLC v. Oracle Am., Inc., 593 U.S. 1, 26, 40 (2021)。
[^135]: 同前注。
[^136]: Dr. R. Li, When the Student Surpasses the Teacher: Why Smaller Models Sometimes Win in Distillation, MEDIUM（2025年4月16日），https://medium.com/genai-in-real-world/when-the-student-surpasses-the-teacher-why-smaller-models-sometimes-win-in-distillation-a597605aa085。
[^137]: 参见 Doe 1 v. GitHub, Inc., 672 F. Supp. 3d 837 (N.D. Cal. 2023)；另参见 Dave Simpson, GitHub Users Say Microsoft Ripped Off Their Code for AI Tool, LAW360（2022年11月3日），https://www.law360.com/articles/1546590/github-users-say-microsoft-ripped-off-their-code-for-ai-tool；Doe v. GitHub, Inc., BAKER HOSTETLER, https://www.bakerlaw.com/the-copilot-litigation/。
[^138]: 参见 Doe 1, 672 F. Supp. 3d 837 (N.D. Cal. 2023)。
[^139]: 同前注，第846页。
[^140]: Mark A. Lemley & Peter Henderson, The Mirage of Artificial Intelligence Terms of Use Restrictions, 100 IND. L.J. 1327 (2025)。
[^141]: 同前注，第1331页。
[^142]: 同前注，第1330页。
[^143]: Terms of Use, OPENAI（2024年12月11日），https://openai.com/policies/row-terms-of-use/（“您不得将我们的服务用于任何非法、有害或滥用性活动。例如，您不得……以自动或程序化方式提取数据或输出……”）。
[^144]: Lemley & Henderson，前注140，第1341–42页（列举设有此类条款的公司实例）；对照 No Reverse Engineering: Overview, Definition, and Example, COBRIEF（2025年4月9日），https://www.cobrief.app/resources/legal-glossary/no-reverse-engineering-overview-definition-and-example（该文展示了禁止反向工程条款可能的样子）。
[^145]: 参见 Bowers v. Baystate Techs., Inc., 320 F.3d 1317 (Fed. Cir. 2003)。
[^146]: 例如参见 Business Terms, OPENAI（2025年5月31日），https://openai.com/policies/business-terms/。
[^147]: 同前注。
[^148]: Van Buren v. United States, 593 U.S. 374, 382–83 (2021)。
[^149]: 参见 hiQ Labs, Inc. v. LinkedIn Corp., 31 F.4th 1180 (9th Cir. 2022)。
[^150]: 参见 Register.com, Inc. v. Verio, Inc., 356 F.3d 393 (2d Cir. 2004)。
[^151]: 17 U.S.C. § 102(a)。
[^152]: 参见 Copyright Registration Guidance: Works Containing Material Generated by Artificial Intelligence, 88 Fed. Reg. 16190, 16191–93（2023年3月16日）；另参见 Naruto, 888 F.3d 418 (9th Cir. 2018)（确认只有人类才能享有版权）。
[^153]: William Plomer 语，转引自 GLYN MAXWELL, ON POETRY 45 (2012)。
[^154]: Alex Shipps, LLMs Develop Their Own Understanding of Reality as Their Language Abilities Improve, MASS. INST. OF TECH.（2024年8月14日），https://news.mit.edu/2024/llms-develop-own-understanding-of-reality-as-language-abilities-improve-0814。
[^155]: 同前注。
[^156]: Copyright Registration Guidance: Works Containing Material Generated by Artificial Intelligence, 88 Fed. Reg. 第16192–93页。
[^157]: 参见 Thaler v. Perlmutter, 130 F.4th 1039 (D.C. Cir. 2025)（维持对缺乏人类创作的 AI 生成艺术作品拒绝登记的决定）。
[^158]: Sam Altman Faces Crossroads: OpenAI's Closed-Source Dilemma as DeepSeek Paves Open Path, OPENTOOLS, https://opentools.ai/news/sam-altman-faces-crossroads-openais-closed-source-dilemma-as-deepseek-paves-open-path（最后更新于2025年2月5日）。
[^159]: Craig S. Smith, DeepSeek: How China's AI Innovators Are Challenging the Status Quo, FORBES（2025年1月22日），https://www.forbes.com/sites/craigsmith/2025/01/22/deepseek-how-chinas-ai-innovators-are-challenging-the-status-quo/。
