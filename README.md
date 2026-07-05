# Agentic CI/CD Security

A practical security knowledge base and hardening framework for identifying, auditing, and securing CI/CD workflows that integrate AI coding agents, autonomous repository bots, and LLM-powered development automation.

As AI agents are increasingly granted access to codebases, pull requests, issues, workflow runners, and development tools, they introduce new software supply-chain risks. This repository maps those risks and documents concrete engineering defenses for safer agentic software delivery.

---

## Project Roadmap

- [x] Establish Core Threat Model & Attack Vectors
- [ ] Publish GitHub Actions Enforcement Guidelines (`/checklists`)
- [ ] Document Vulnerable vs. Hardened Workflow Reference Patterns (`/examples`)
- [ ] Standardize Core Policy Specifications for Autonomous CI Contexts
- [ ] Research Automated Detection & Static Analysis Baselines (`AegisCI`)

---

## Core Threat Model

AI agents operating within software delivery pipelines often read untrusted context while operating near privileged environments. Common untrusted inputs include:

- Pull request titles and descriptions
- Issue bodies and comments
- Commit messages
- Repository markdown files
- Configuration files
- Code comments
- External documentation
- Generated logs or artifacts

This creates several distinct risk areas:

### Untrusted Context Flow
Poisoned pull request content, malicious markdown, or injected commit messages may attempt to alter agent behavior.

### Excessive Token Permissions
Agents may run with repository tokens that allow write access, pull request modification, issue comments, release creation, or workflow changes.

### Unsafe Tool Execution
Agents may execute shell commands, run package managers, call external tools, or modify files based on untrusted input.

### Secret Exposure
Environment variables, API keys, cloud credentials, package registry tokens, and deployment secrets may become visible to agent tools or logs.

### Unsafe Output Handling
Agent-generated patches, comments, workflow changes, or release steps may be trusted without sufficient human review.

---

## Repository Structure

```text
.github/workflows/   # CI workflows for validating the repository itself.
checklists/          # Actionable security checklists for reviewing agentic CI/CD workflows.
examples/            # Vulnerable and hardened workflow examples.
threat-models/       # Threat models for common AI-agent software delivery patterns.
resources/           # Curated tools, standards, papers, and case studies.
```

### Defensive Tools and Frameworks
*   [mcp-context-protector](https://github.com/trailofbits/mcp-context-protector) — A Trail of Bits security wrapper enforcing prompt injection and context manipulation defenses directly at the tool server layer.
*   [Agentic Actions Auditor](https://github.com/trailofbits/skills/tree/main/plugins/agentic-actions-auditor) — Trail of Bits plugin designed to perform static security analysis on GitHub Actions workflows invoking AI coding agents (such as Claude Code or Gemini CLI) to identify injection paths.
*   [Defenter](https://github.com/example/defenter) — A semantic monitoring proxy designed to sit between CI runners and LLM providers to detect real-time context contamination.

### Standards and Security References
*   [OWASP Top 10 for Agentic Applications](https://owasp.org/www-project-mcp-top-10/) — The emerging baseline risk framework for agentic applications and systemic integrations.
*   [Model Context Protocol Specification](https://modelcontextprotocol.io) — Core openspec guidance outlining strict input validation and human-in-the-loop (HITL) baselines.


### Contributing
Contributions are welcome. Please keep submissions practical, security-focused, and clearly sourced where possible. Review CONTRIBUTING.md for formatting rules.

### License
This project is licensed under the MIT License.