# danao-brain (MCP remote server)

danao 智能组织大脑的 **MCP 远程服务器**挂牌仓库（元数据仓——运行代码私有，本仓只承载 MCP Registry 所需的公开元数据与接入文档）。

## 接入（三步）

1. **发现**：`GET https://danao.tongqiansuanzhi.com/.well-known/agent-card.json`（Ed25519 签名卡，RFC 8037 JWK）
2. **调用**：`POST https://danao.tongqiansuanzhi.com/mcp`（Streamable HTTP，`X-API-Key: dk_live_...`，scope 制）
3. **治理**：高危 `capability_call` 走异步审批（`GET /api/v1/approvals/pending`）+ 预算闸 + append-only 审计哈希链（每日链尾 Ed25519 签名锚定）

## 工具面（scope 过滤后）

`kb_*`（知识库检索/问答/入库）· `capability_*`（跨项目能力总库）· `brain_status` · `experience_recall` · `memory_search` · `agent_delegate` 等

## 完整接入文档

见生产仓 `docs/ACCESS-danao-agent.md`（等价内容：https://danao.tongqiansuanzhi.com/api/version 可验证在线态）。

## License

元数据与文档：MIT。danao 运行代码：私有（本仓不含）。
