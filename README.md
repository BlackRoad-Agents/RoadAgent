# RoadAgent — BlackRoad Agent Framework

> Forked from [Mastra](https://github.com/mastra-ai/mastra). The TypeScript agent framework powering BlackRoad OS.

**RoadAgent** is how you build, deploy, and manage AI agents on BlackRoad infrastructure. Suspend/resume execution, built-in RAG, MCP tool support, and fleet-native deployment.

## Features

- **Suspend/Resume**: Agents can pause mid-execution and resume later
- **Built-in RAG**: Automatic context retrieval from RoadMem + Qdrant
- **MCP Support**: Model Context Protocol for tool calling
- **Fleet-native**: Deploy to any Pi node with `br deploy agent`
- **35 Named Agents**: Pre-configured personas with unique models and skills
- **NATS Messaging**: Agent-to-agent communication via CarPool

## Quick Start

```typescript
import { Agent } from '@blackroad/agent';

const alice = new Agent({
  name: 'Alice',
  role: 'Gateway',
  model: 'llama3.2',
  memory: 'roadmem://alice',
  node: '192.168.4.49'
});

const response = await alice.chat('What is the fleet status?');
```

## Architecture

```
RoadAgent Framework
├── Agent Runtime (suspend/resume, lifecycle)
├── RoadMem Integration (persistent memory)
├── RAG Pipeline (Qdrant vectors + context)
├── MCP Tools (file, shell, git, fleet)
├── NATS Pub/Sub (CarPool messaging)
└── Fleet Deployment (any Pi node)
```

---

© 2026 BlackRoad OS, Inc. Fork of Mastra (Apache 2.0). BlackRoad customizations proprietary.
