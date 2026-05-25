# Web Search Skill

Retrieves real-time web content via Anthropic's built-in `web_search` tool.

## Metadata

- **Category**: search
- **Provider**: Anthropic (`web_search` built-in tool)
- **Status**: active

## Capabilities

- Real-time web search with result ranking
- URL content retrieval
- Competitive intelligence gathering
- Regulatory and news monitoring
- Market pricing and benchmark research

## Agents That Use This Skill

- Workflow Advisor (for identifying external best practices and benchmarks)

## Integration

Enable via Anthropic API beta header `anthropic-beta: web-search-2024-11-05` or the Claude Agent SDK `web_search` tool config.

## Guardrails

- Do not use to retrieve or process personally identifiable information
- Treat results as informational — not authoritative for compliance decisions
- Cite sources when using web content in outputs
