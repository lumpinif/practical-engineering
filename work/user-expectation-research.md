# 用户期待与 Practical Engineering：研究结论

调研日期：2026-08-31

## 结论

这条原则值得吸收，而且它不是 UI 审美偏好：**一个实现即使业务逻辑自洽，只要它让目标用户合理地预测错了下一步、结果或恢复方式，就仍可能是用户层面的缺陷。** ISO 9241-110 把“符合用户期待”列为跨技术、跨领域的交互原则，并把可用性同时定义为有效性、效率与满意度；它还明确把系统的意外响应列为可能导致伤害的可用性问题。[ISO 9241-110:2020](https://www.iso.org/standard/75258.html) · [ISO 在线预览](https://www.iso.org/obp/ui?_escaped_fragment_=iso%3Astd%3Aiso%3A9241%3A-110%3Adis%3Aed-2%3Av1%3Aen)

用户不是空白地进入产品。他们会用现实世界、同类软件、目标平台以及产品自身过去的行为，形成对“这是什么、点了会怎样、如何返回”的心理模型。偏离这些模型会增加学习成本和认知负担，也更容易造成误操作、迷失和放弃任务。[NN/g：Mental Models](https://www.nngroup.com/articles/mental-models/) · [NN/g：Consistency and Standards](https://www.nngroup.com/articles/consistency-and-standards/)

这也是可访问性问题，不只是“普通用户体验”。WCAG 的 Predictable 指南解释了：位置和行为不一致会让认知障碍、屏幕阅读器、屏幕放大器及动作受限用户更难理解和完成任务；W3C 的认知无障碍指南进一步建议采用熟悉的控件、affordance、布局和视觉层级。[WCAG 2.2：Predictable](https://www.w3.org/WAI/WCAG22/Understanding/predictable) · [W3C：Use a Familiar Hierarchy and Design](https://www.w3.org/WAI/WCAG2/supplemental/patterns/o1p02-familiar-design/)

## 应吸收的通用原则

以下内容是跨项目、跨平台成立的工程判断：

1. **正确性包括用户可预测性。** 不只检查系统内部是否按规格执行，也检查目标用户是否能从名称、外观、位置、反馈、既有产品行为和常见惯例，合理预测操作的含义与后果。
2. **先借用用户已经会的东西。** 同一个功能在产品内保持相同名称和行为；通用任务优先采用目标平台与行业里已经成熟的模式。Apple 认为熟悉性和一致性让人更快学会并更有信心；Microsoft Fluent 同样主张先基于平台原生、熟悉的组件与模式，再把精力放在真正有价值的特色体验。[Apple Design Principles](https://developer.apple.com/design/human-interface-guidelines/design-principles) · [Fluent 2 Design Principles](https://fluent2.microsoft.design/design-principles)
3. **期待落差是一种真实用户伤害。** 它可能不是数据泄露或崩溃，但会让用户做错事、找不到功能、误以为操作成功、失去上下文、重复劳动或不再信任产品。对高后果、不可逆、数据与隐私相关操作，预期与实际结果必须尤其一致。
4. **一致不等于机械相同。** 相同功能需要稳定识别；不同功能不能为了视觉统一而强行使用相同标签。WCAG 3.2.4 明确区分“consistently”与“identically”：名称可随上下文变化，但必须让功能关系仍然清楚。[WCAG 2.2：Consistent Identification](https://www.w3.org/WAI/WCAG22/Understanding/consistent-identification)
5. **目标用户和真实上下文决定期待，不是设计者的个人习惯。** 心理模型来自用户背景和经历，不同用户群可能不同；有分歧或高风险时应看现有行为、平台规范、同类产品和最小真实用户证据，而不是凭团队直觉宣布“用户应该懂”。

## 通用原则与平台惯例的边界

- **通用原则**是：行为可预测、名称与含义一致、反馈与结果相符、用户能保持控制、重要后果可理解且可恢复。这些可以进入 Practical Engineering。
- **平台或行业惯例**是：返回手势、菜单位置、对话框按钮顺序、图标、快捷键、导航结构等。它们是判断某个项目中用户期待的证据，不应被 Skill 写死为跨平台规则。ISO 本身也区分了通用交互原则与由 Apple、Microsoft 等平台指南定义的具体约定。[ISO 在线预览](https://www.iso.org/obp/ui?_escaped_fragment_=iso%3Astd%3Aiso%3A9241%3A-110%3Adis%3Aed-2%3Av1%3Aen)
- **产品内部习惯**也构成真实期待。即使外部没有统一惯例，产品已经反复建立的名称、流程、返回行为和数据语义，也不应在一个局部功能里无提示改变。

因此，Skill 应要求工程师**识别当前项目适用的期待来源**，而不是自己维护一张永远过时的 UI 规范清单。

## 什么时候可以故意偏离

偏离惯例不是绝对禁止，但需要满足更高证据门槛。合理情况包括：

- 惯例与安全、隐私、数据正确性、无障碍或明确产品契约冲突；
- 惯例已经不被目标用户识别，或不适合当前设备、输入方式和任务；
- 新方案对核心任务有明确且足够大的效率或理解收益，而不是只为了新奇、品牌感、技术方便或少写代码；
- 新模型能通过界面本身被理解，有清楚反馈，并对高后果操作提供确认、撤销或恢复；
- 对重要偏离有与风险相称的真实用户证据，而不只是设计者自信。

NN/g 的建议是：只有新方式对任务确有必要或明显提高效率时，才值得承担额外认知负担；心理模型存在很强惯性，创新应当“明显优于”旧方式。ISO 则明确要求根据用户、任务、环境、交互技术和使用后果做情境化取舍。[NN/g：Consistency and Standards](https://www.nngroup.com/articles/consistency-and-standards/) · [NN/g：Mental Models](https://www.nngroup.com/articles/mental-models/) · [ISO 在线预览](https://www.iso.org/obp/ui?_escaped_fragment_=iso%3Astd%3Aiso%3A9241%3A-110%3Adis%3Aed-2%3Av1%3Aen)

## Practical 的最小判断法

不需要新增评审表或固定仪式。遇到用户可见行为时，只补三个问题：

1. 目标用户看到这个名称、控件、位置和当前状态，会合理预测什么？
2. 实际结果是否兑现这个预测，尤其是 Save、Delete、Back、Cancel、Close、Send、支付、权限和数据变更？
3. 如果必须不同，差异带来的真实收益是什么，用户如何在操作前理解它、操作后恢复它？

例子：用户在全屏弹层中按 Back，通常是在表达“退出当前弹层并回到刚才的内容”。如果实现把他直接带到更早的页面，路由逻辑可能完全按代码设计运行，但它破坏了用户的导航模型、丢失上下文，因此仍是应修的行为问题。[NN/g：Mental Models 的 Back 示例](https://www.nngroup.com/articles/mental-models/)

## 对当前 Skill 的落地建议

建议**新增一个很短、可被一眼发现的章节**，而不是把它埋进 `Work From the Outcome` 的一个长 bullet，也不要建立 UI/UX checklist。这个问题是现有 Skill 未明确覆盖的独立失败类型，但只需要 3 条判断，不需要新流程。

建议放在 `Work From the Outcome` 之后，暂名 `Honor the User's Model`：

```markdown
## Honor the User's Model

- Treat a user-visible behavior as incorrect when it is internally valid but
  violates a reasonable expectation created by its language, appearance,
  location, platform or domain conventions, or the product's own behavior.
- Start from the target users' learned model. Prefer familiar controls and
  interactions, keep the same concept consistent, and verify platform-specific
  conventions in the project's actual context rather than treating them as
  universal rules.
- Depart from an established expectation only for a concrete user benefit or
  constraint that outweighs the learning and error cost. Make the difference
  understandable before it matters, preserve feedback and recovery, and seek
  proportional user-facing evidence when the consequence is significant.
```

这三条会补强现有 Skill，但不会官僚化：它没有固定流程、没有强制用户研究、没有平台规则表，也不会把每个视觉差异升级成 bug。它只是把“用户合理期待”纳入结果正确性，并把故意偏离的举证责任放回设计与实现一方。

## 不应吸收的内容

- 不要把某个平台的控件位置、按钮顺序或手势写成全球通用规则。
- 不要要求所有功能都做正式访谈、可用性实验或竞品报告。
- 不要把“一致”理解成所有页面视觉完全相同，或阻止确有价值的创新。
- 不要让“用户期待”成为不修安全、数据、隐私或真实产品契约问题的借口。
- 不要以“用户应该习惯”为由，把解释成本和误操作风险转嫁给用户。
