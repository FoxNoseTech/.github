## The agent-native knowledge API

Agents do not fail because the model is weak. They fail because the knowledge
layer underneath them is four services glued together: a vector database, an
embedding pipeline, a sync job, and a hand-written MCP server that drifts out
of sync with all three.

FoxNose is one managed service that replaces that stack. REST and MCP from the
same endpoint, over the same data, with the same schema.

### What it does

- **Hybrid search.** Vector similarity, full-text matching and structured
  filters resolve in a single query, not three you merge yourself.
- **Auto-embeddings.** Documents are embedded on write. There is no pipeline
  to run and nothing to backfill when a document changes.
- **Knowledge MCP.** Every collection gets a generated MCP server with a fixed
  tool surface and JSON Schema introspection, so an agent discovers the shape
  of your data instead of being told about it in a prompt.
- **Schema versioning.** Pin an agent to a schema version and migrate the
  collection without breaking it mid-flight.
- **Multi-tenant by default.** Per-key scopes, collection isolation, RBAC and
  30-day immutable audit logs.

Works with OpenAI, Anthropic and Google models, with LangChain and Ollama, and
with MCP clients including Claude Code, Claude Desktop, Cursor, Cline and
Continue.

### Repositories

| Repository | What it is |
| --- | --- |
| [foxnose-python](https://github.com/FoxNoseTech/foxnose-python) | Official Python SDK. On PyPI as [`foxnose-sdk`](https://pypi.org/project/foxnose-sdk/). |
| [foxnose-typescript](https://github.com/FoxNoseTech/foxnose-typescript) | Official TypeScript SDK. |
| [langchain-foxnose](https://github.com/FoxNoseTech/langchain-foxnose) | LangChain integration for Python: retriever and vector store. |
| [langchain-foxnose-js](https://github.com/FoxNoseTech/langchain-foxnose-js) | LangChain integration for JavaScript and TypeScript. |

### Start here

- [foxnose.net](https://foxnose.net) — what it is and who it is for
- [Documentation](https://foxnose.net/docs) — quickstart, API reference, MCP setup
- [Pricing](https://foxnose.net/pricing) — free tier, no card
- [Blog](https://foxnose.net/blog) — how the thing is built

Questions, bug reports and integration requests: open an issue on the relevant
repository, or write to support@foxnose.net.
