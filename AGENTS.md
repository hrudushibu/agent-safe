# Agent Safe — AI Agent Rules

This file provides guidance to AI agents working on Agent Safe, an open-source security gateway for AI agents and MCP tools.

## 🎯 Project Context

**Agent Safe** is a security control plane for AI agents. When contributing to this project, you're building the infrastructure that makes AI agents safer to deploy in production.

- **Repository**: [https://github.com/hrudushibu/agent-safe](https://github.com/hrudushibu/agent-safe)
- **License**: Apache-2.0
- **Contact**: [hrudushibu.tech@gmail.com](mailto:hrudushibu.tech@gmail.com)

## 🚧 Development Stage

**Early Development** — Core architecture is being designed. Implementation is in progress. Folder structure, data models, and feature specifications are not yet finalized.

## 🏗️ Architecture Principles

### Security-First Design
Every feature should consider the security implications. This project protects against dangerous AI agent behavior—our code must be bulletproof.

### Policy-Driven Logic
Business logic should be expressed as declarative policies, not imperative code. This makes behavior auditable and modifiable without code changes.

### Human-in-the-Loop
Always preserve human control. Features that bypass human oversight need exceptional justification.

### Audit Everything
Every decision, every tool execution, every policy evaluation should be logged. Security teams need complete visibility.

## 💻 Tech Stack

- **Next.js 16** with App Router
- **React 19** with Server Components
- **TypeScript 5** in strict mode
- **Tailwind CSS 4** for styling
- **shadcn/ui** for UI primitives

## 📝 Code Style Guidelines

### TypeScript
```typescript
// ✅ Good: Explicit types, clear naming
interface ToolExecutionRequest {
  agentId: string;
  toolName: string;
  parameters: Record<string, unknown>;
  context: ExecutionContext;
}

// ❌ Bad: Implicit any, unclear naming
function execute(req: any) {
  // ...
}
```

### React Components
```typescript
// ✅ Good: Named export, typed props
interface PolicyEditorProps {
  policyId: string;
  onSave: (policy: Policy) => void;
}

export function PolicyEditor({ policyId, onSave }: PolicyEditorProps) {
  // ...
}

// ❌ Bad: Default export, untyped props
export default function Editor(props) {
  // ...
}
```

### Security Logic
```typescript
// ✅ Good: Fail-safe defaults, explicit denial
function checkPermission(agent: string, tool: string): boolean {
  const permission = permissions.get(agent, tool);
  
  // Deny by default
  if (!permission) return false;
  
  // Explicit checks
  if (permission.denied) return false;
  if (permission.requiresApproval) return false;
  
  return permission.allowed === true;
}

// ❌ Bad: Optimistic defaults
function checkPermission(agent: string, tool: string) {
  return permissions.get(agent, tool)?.allowed ?? true; // Dangerous!
}
```

## 📂 Current Project Structure

```
app/                  # Next.js App Router pages
components/
  app/                # App-wide layouts (header, footer)
  console/            # Console-specific UI (sidebar, nav)
  ui/                 # Base UI primitives (shadcn/ui)
lib/                  # Shared utilities
```

**Note**: Specific feature folders (policies, audit, approvals, etc.) will be added as development progresses.

## 🚨 Security Considerations

### Never Trust Agent Input
Treat all agent-provided data as untrusted. Validate, sanitize, and scope-check everything.

### Fail Closed
When in doubt, deny. Availability is less important than security in this project.

### Log Before Action
Audit log entries should be written *before* executing the action, not after.

### Immutable Audit Trail
Once written, audit logs should never be modified or deleted.

## 🔄 Contribution Workflow

1. Review existing design discussions in issues
2. Consider security implications of every change
3. Follow TypeScript strict mode requirements
4. Write tests for security-critical paths
5. Document security decisions

---

<!-- BEGIN:nextjs-agent-rules -->

# This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` (resolved from this file's directory; in monorepos the `next` package may not be visible from the repo root) before writing any code. Heed deprecation notices.

This block is written and re-added by `next dev` — verify at `node_modules/next/dist/server/lib/generate-agent-files.js`. Removing it from a diff only re-creates the uncommitted change; committing it with your work keeps the tree clean.

<!-- END:nextjs-agent-rules -->
