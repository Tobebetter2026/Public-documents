<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>电感设计专家 - Inductor Design Pro</title>
  <style>
    body { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif; font-size: 18px; line-height: 1.6; max-width: 720px; margin: 2em auto; padding: 0 1em; color: #333; }
    h1 { font-size: 1.75em; }
    h2 { font-size: 1.35em; margin-top: 1.5em; }
    a { color: #0969da; }
  </style>
</head>
<body>
  <h1>电感设计专家</h1>
  <p style="margin-top: 0; color: #666; font-size: 0.95em;">最后更新：2026-06-14</p>
  <p><strong>电感设计专家</strong> 为 Buck / Boost / Forward 正激副边输出滤波 / 交错 Buck（多相）等功率电感提供从规格与约束、磁芯与绕组联合迭代，到汇总报告与导出的完整工作流；计算在设备本地完成，设计数据不向开发者服务器上传。</p>
  <p>本说明面向从 <strong>App Store</strong> 安装的应用（iPhone / iPad / Mac，以实际上架为准）。应用提供 <strong>14 天全功能试用</strong>，之后需通过 App Store <strong>年度订阅</strong>继续使用完整能力；具体以应用内为准。</p>

  <h2>主要功能概览</h2>
  <ul>
    <li>Buck / Boost / Forward（仅设计正激副边输出滤波电感，不设计正激变压器）/ 交错 Buck（多相，每相一颗电感），支持 CCM / DCM / BCM、AP 与 LI² 等选型辅助</li>
    <li>磁芯 × 线规（含利兹线）<strong>联合迭代</strong>，多种损耗模型（Steinmetz、厂商曲线/表、铁粉官方公式等，依材料类型选用）</li>
    <li>硬性约束筛选后，<strong>帕累托非支配筛选 + DQS 五维综合评分</strong>（损耗、磁芯体积、热裕量、可制造性、风险）排序，多组备选方案自动对比</li>
    <li><strong>参数探索</strong>：频率扫描与纹波率 / DCM 扫描图表，可视化辅助权衡频率与磁芯尺寸</li>
    <li><strong>PDF / JSON</strong> 报告与设计文件导出</li>
    <li><strong>「我的数据库」</strong>：本机维护材料、磁芯、骨架，支持<strong>批量导入/导出</strong>，与内置库一并参与选型；<strong>不上传服务器</strong>。</li>
  </ul>

  <h2>使用流程（三步）</h2>
  <ol>
    <li><strong>规格与约束</strong>：输入电气规格与设计约束，通过预检后进入下一步。<strong>磁密上限 B<sub>max</sub> 为可选项</strong>：留空时按所选材料与工作温度自动确定有效磁密限值；若手动填写，请按材料族合理取值——不宜沿用铁氧体常用的偏低数值（如 0.35 T）用于磁粉芯，否则可能在预筛阶段过早排除本可行的磁芯方案。</li>
    <li><strong>磁芯与绕组</strong>：联合迭代选型、方案比较与确认</li>
    <li><strong>汇总与报告</strong>：损耗与温升等汇总、设计文件与报告导出</li>
  </ol>

  <h2>常见问题</h2>
  <ul>
    <li><strong>如何开通订阅？</strong>点击底部（iPhone）或顶部（iPad）第3个标签<strong>「订阅」</strong>，付费方案界面将直接弹出；按提示通过 <strong>Apple</strong> 完成订阅，或点<strong>「恢复购买」</strong>恢复已有订阅。</li>
    <li><strong>能否离线使用？</strong>核心计算可离线；App Store 订阅相关操作需网络。</li>
    <li><strong>技术支持：</strong><a href="https://github.com/Tobebetter2026/InductorDesignPro/issues/new/choose">GitHub Issues</a></li>
  </ul>

  <h2>开发与协作约定</h2>
  <p>以下约定适用于在本仓库内改代码的开发者与 AI 助手，<strong>任务完成时必须执行，无需再向用户确认是否提交</strong>。</p>
  <ol>
    <li><strong>同步文档（必做）</strong>：每次代码变更完成后，按根目录 <code>CLAUDE.md</code>「文档同步规则」更新对应文档；至少更新 <code>CHANGELOG.md</code>；涉及计算公式 / 物理模型 / 算法逻辑时，还必须更新 <code>InductorDesignProForBuckAssDocs/02_analysis_reports/计算公式分析与验证报告.md</code> 对应章节。</li>
    <li><strong>验证（必做）</strong>：提交前运行 <code>npm test -- --run</code> 与 <code>npm run build</code>，确保通过。</li>
    <li><strong>Git 提交（必做）</strong>：文档与代码一并纳入同一提交（或逻辑上拆分的连续提交）；写清楚 commit message 的「为什么」；<strong>不要每次询问用户是否提交</strong>——除非用户明确要求「只改不提交」或「先不要 commit」。</li>
    <li><strong>推送</strong>：默认仅提交到本地；推送到 <code>origin</code> 或开 PR 仅在用户明确要求时执行。</li>
  </ol>
  <p>更细的代码规范、单位约定与常见坑点见 <code>CLAUDE.md</code>。</p>

  <h2>链接</h2>
  <p><a href="https://github.com/Tobebetter2026/InductorDesignPro/issues/new?template=bug_report.md">Bug 报告</a> · <a href="https://github.com/Tobebetter2026/InductorDesignPro/issues/new?template=feature_request.md">功能建议</a></p>
  <hr>
  <p><a href="privacy-policy.html">隐私政策</a></p>
  <p>开发者：Xu Jianzhong · © 2026. All rights reserved.</p>
</body>
</html>
