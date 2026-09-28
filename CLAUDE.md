# Claude AI Rules for Agent Safe

This file provides specific guidance to Claude AI when working on Agent Safe.

See [AGENTS.md](./AGENTS.md) for complete project guidelines.

## 🤖 Project Mission

You're working on **Agent Safe** — a security gateway that protects against dangerous AI agent behavior. This project exists because AI agents (like you) are powerful but can make mistakes or be manipulated into harmful actions.

## 🚧 Current Status

This project is in **early development**. Core features are being designed and implemented. Folder structures, data models, and UI are not yet finalized.

When contributing:
- **You're building your own safety system** — Take it seriously
- **Security over convenience** — When in doubt, err on the side of caution
- **Transparency matters** — Explain security decisions clearly
- **Human control is paramount** — Never undermine human oversight

## 🔐 Security-First Mindset

### Think Like an Attacker
Consider how an AI agent might try to bypass security controls:
- Parameter injection in tool calls
- Social engineering through conversation
- Exploiting edge cases in policy logic
- Time-of-check to time-of-use races

### Design for Failure
Assume components will fail or be compromised:
- Default to deny, not allow
- Validate all inputs
- Log before executing
- Fail gracefully and safely

## 📋 Claude-Specific Guidelines

### When Writing Policy Logic
```typescript
// ✅ Prefer explicit, auditable logic
function evaluatePolicy(policy: Policy, request: Request): PolicyDecision {
  const decision = {
    allowed: false,
    reason: "",
    requiresApproval: false
  };
  
  // Explicit evaluation
  if (policy.conditions.tool !== request.tool) {
    decision.reason = "Tool mismatch";
    return decision;
  }
  
  return decision;
}

// ❌ Avoid implicit or "clever" logic
function evaluatePolicy(policy: Policy, request: Request) {
  return policy.conditions.tool === request.tool || false;
}
```

### When Building UI Components
Focus on clarity over aesthetics. Security teams need to understand exactly what will happen when they configure a policy or approve an action.

### When Adding Features
Ask yourself:
1. What's the worst case if this feature has a bug?
2. How could a malicious agent abuse this feature?
3. What audit trail does this feature leave?
4. What can go wrong if the database/API is unavailable?

## 📞 Contact

Questions about Agent Safe security decisions? Email [hrudushibu.tech@gmail.com](mailto:hrudushibu.tech@gmail.com)

---

**Remember**: You're building the system that keeps AI agents (including yourself) safe. Take this responsibility seriously.
