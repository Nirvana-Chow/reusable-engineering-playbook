# 固定版本、候选验收与可恢复发布

- ID：deployment-versioned-release。
- 环节：部署 / CI/CD / 数据。
- 卡片版本：0.1；来源核对：2026-10-24。
- 状态：候选，未完成公开独立复现。

用途：让部署对象、验收证据和恢复目标相对应，避免测试版本与发布版本不同。

条件：能标识源码和产物，有隔离候选环境，能核对数据兼容性。平台、运行时、数据库与构建工具未选定；复现时记录提交、产物摘要、环境和迁移版本，不公开真实地址或凭据。

## 候选步骤

1. 固定源码与构建产物，记录依赖版本。
2. 使用隔离数据部署明确标注的候选。
3. 分开验证访问、身份、关键操作及外部依赖。
4. 保存通过、失败和未测项，证据对应同一版本。
5. 验证旧版本与数据结构的兼容性，明确恢复目标。
6. 完成验收和必要批准后发布，随后读回实际版本并复测主流程。

验收：对象可追溯、证据对应、主流程实际执行、恢复方案有记录。单个健康检查不代表完整功能通过。

局限：应用回退不等于数据回退，迁移可能使旧版本不可用；环境保护能力须按实际套餐和仓库类型核对。本卡没有实测证据。

来源：[GitHub 部署控制](https://docs.github.com/en/actions/how-tos/deploy/configure-and-manage-deployments/control-deployments)、[部署审核](https://docs.github.com/en/actions/how-tos/deploy/configure-and-manage-deployments/review-deployments)、[安全参考](https://docs.github.com/en/actions/reference/security/secure-use)。本卡为原创方案，不包含第三方工作流，使用实现时另核对许可。
