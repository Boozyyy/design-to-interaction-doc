# Design to Interaction Doc

一个用于设计交付阶段的 Codex skill：读取已经完成的设计稿、原型或截图，生成给研发的简洁中文交互文档。

它遵循一个核心判断：如果研发只看设计稿，可能做出两种不同的合理实现，就用一句话补充说明；设计稿已经表达清楚的内容不再复述。

## 适用场景

- 根据 Figma、原型、截图或 PDF 整理研发交互说明
- 补充返回与数据保留、筛选范围、默认状态、操作限制等隐含规则
- 说明跨页面、跨端联动和流程中断后的行为
- 基于新版设计更新已有交互文档

这个 skill 不负责从零设计产品，也不把静态界面中无法判断的业务规则写成确定结论。

## 安装

克隆仓库后，将本目录复制到 Codex skills 目录：

```bash
cp -R design-to-interaction-doc ~/.codex/skills/
```

重新启动 Codex 或开启新任务，使 skill 被重新发现。

## 使用

可以显式调用：

```text
使用 $design-to-interaction-doc，根据这些设计稿生成给研发的交互文档。
```

也可以直接描述任务并附上设计材料：

```text
请根据这组设计稿整理交互说明。只写研发无法从画面直接判断的关键规则，输出为 Word。
```

建议同时提供：

- 已完成的设计稿、原型、截图或设计导出文件
- 已知的产品需求或业务规则
- 旧版交互文档（如需更新）
- 希望的输出格式；未指定时通常生成 DOCX

## 输出特点

- 按功能模块组织，不机械罗列所有页面和控件
- 以短句描述条件、操作、结果和状态变化
- 只在复杂流程或对照场景中使用表格
- 未确定的规则就地标为“待确认”或“待讨论”
- 设计截图按需放在相关说明附近

具体执行规则见 [`SKILL.md`](SKILL.md)，写作风格和轻量结构见 [`references/`](references/)。

## 仓库结构

```text
design-to-interaction-doc/
├── README.md
├── LICENSE
├── SKILL.md
└── references/
    ├── document-template.md
    └── writing-style.md
```

## License

[MIT](LICENSE)
