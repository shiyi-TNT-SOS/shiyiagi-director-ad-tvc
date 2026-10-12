# shiyiagi-director-ad-tvc · 广告片 AI 视频导演提示词

> 把「让 AI 扮演广告片导演」从口号固化成可复用的四层提示词结构。专治 AI 出的广告创意「太空、全是形容词、落不了地」。

## 它解决什么

把导演能力拆成四层，缺一层就废一级：

| 层 | 作用 | 缺了会怎样 |
|---|---|---|
| 01 身份锚定 | 给 AI 一个具体的审美立场和工作顺序 | 输出大众审美平均值 |
| 02 镜头语法 | 强制每个镜头覆盖 7 个维度 | AI 只会说"唯美的画面" |
| 03 输出契约 | 定死表格字段、镜数、时长 | 输出散文，没法直接用 |
| 04 边界约束 | 禁词 + 物理可行性 + 合规 | 混进空话和拍不出来的镜头 |

> 真正决定质量的是 **镜头语法** 和 **输出契约**——维度给了，AI 就没法糊弄。

## 核心方法

- **一个卖点原则**：一条片只讲一件事，视觉母题贯穿全片。
- **钩子结构**：信息流前 3 秒抓眼球 vs 电视慢铺陈，两种开头策略。
- **导演人设三要素**：流派 + 审美信条 + 工作顺序（见 `director-personas.md`）。
- **概念转译法**：调性词（高级 / 温暖 / 炸裂）→ 镜头 / 构图 / 运镜 / 光线 / 色彩 / 材质 六类元件，绝不写废词。

## 交付物

- **导演提示词** → 喂给 LLM，产出广告结构 + 分镜表
- **单镜头生成提示词** → 喂给视频模型（即梦 / 可灵 / Seedance / Grok）出片

## 目录结构

```
shiyiagi-director-ad-tvc/
├── SKILL.md
├── README.md
└── references/
    ├── director-prompt.md        # 主模板（四要素契约）
    ├── director-personas.md      # 8 类导演人设
    ├── ad-structure.md           # 广告结构 / 记忆点 / 视觉母题 / 钩子
    ├── concept-translation.md    # 调性词六类元件转译
    ├── ai-video-prompt.md        # 七段顺序铁律
    ├── lens-grammar.md           # 镜头语法七维
    ├── compliance.md             # 广告法合规
    ├── production.md             # 生产层结论
    ├── platform-specs.md         # 引擎规格
    ├── style-anchors.md          # 风格锚点
    ├── troubleshooting.md        # 常见翻车与修复
    └── walkthrough-tvc.md        # 15s 高端腕表信息流 TVC 端到端示例
```

## 怎么用

1. 把 `SKILL.md` 作为指令交给 LLM。
2. LLM 按流程产出：广告结构（一个卖点 / 视觉母题 / 钩子）→ 分镜表 → 逐镜提示词。
3. 把逐镜提示词喂给视频模型出片。

## 适用 / 不适用

- ✅ 品牌广告片、TVC、形象片、产品广告、品牌宣传片
- ❌ 选品 / 爆款拆解 / 口播文案 / 投放策略 → `ecommerce-video-workbench`
- ❌ 剧情化带货（要转化 / CTA / 钩子） → `shiyiagi-director-story-selling`
- ❌ 武打 / 动作戏 → `shiyiagi-director-action`

## 版本与授权

- 版本：**v1.4.0**
- 作者：十一AGI（柳十一 / 十一AGI认知圈）
- 授权：学习与非商业用途可自由使用；商用请先联系作者授权。

## 系列导航

| Skill | 定位 |
|---|---|
| **shiyiagi-director-ad-tvc（本仓库）** | 品牌广告片 / TVC / 形象片 |
| [shiyiagi-director-film](https://github.com/shiyi-TNT-SOS/shiyiagi-director-film) | 故事片 / 叙事短片 |
| [shiyiagi-director-story-selling](https://github.com/shiyi-TNT-SOS/shiyiagi-director-story-selling) | 剧情化带货短视频（独立付费发布线） |
| [shiyiagi-director-action](https://github.com/shiyi-TNT-SOS/shiyiagi-director-action) | 武打 / 格斗 / 动作戏 |
