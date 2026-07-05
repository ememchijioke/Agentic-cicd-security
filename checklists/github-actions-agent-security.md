# GitHub Actions AI Agent Security Checklist

A practical checklist for auditing and hardening GitHub Actions workflows that invoke autonomous coding agents or PR triage bots.

### 1. Context Trigger Isolation
- [ ] **Isolate Untrusted Triggers:** Ensure agents triggered by untrusted external events (e.g., `pull_request_target`, `issue_comment`, `issues`) run in an unprivileged, separate workflow job.
- [ ] **Buffer Context Extraction:** Do not pass raw `github.event.pull_request.title` or `github.event.comment.body` directly as environment variables or command-line arguments to the agent runtime. Extract these to a static, sanitized JSON file first.

### 2. Permissions & Token Hardening
- [ ] **Enforce Least Privilege:** Explicitly set `permissions: read-all` or define granular scopes at the job level. Never let an autonomous agent inherit default repository write tokens.
- [ ] **Output Gating:** If the agent needs to generate a patch or comment, restrict the agent runner to a read-only token, and pass its generated payload to a downstream, human-approved workflow gate for execution.