# Agentic CI/CD Security

<p align="center">
  <img src="./assets/agentic-cicd-banner.png" alt="Agentic CI/CD Security Icon" width="220"/>
</p>

<p align="center">
  <strong>A practical security knowledge base and hardening framework for securing AI agents in CI/CD pipelines.</strong>
</p>

<p align="center">
  Checklists, threat models, vulnerable workflow examples, hardened patterns, and curated references for safer agentic software delivery.
</p>

<p align="center">
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License"></a>
  <a href="./CONTRIBUTING.md"><img src="https://img.shields.io/badge/contributions-welcome-brightgreen.svg" alt="Contributions Welcome"></a>
  <a href="https://github.com/emenchijoke/agentic-cicd-security/stargazers"><img src="https://img.shields.io/github/stars/emenchijoke/agentic-cicd-security?style=social" alt="GitHub stars"></a>
  <a href="https://github.com/emenchijoke/agentic-cicd-security/issues"><img src="https://img.shields.io/github/issues/emenchijoke/agentic-cicd-security" alt="Open Issues"></a>
</p>

## Why Agentic CI/CD Security?

AI coding agents are increasingly being integrated into pull request review, issue triage, code modification, documentation generation, testing, and release workflows.

These agents often process **untrusted repository or user-controlled input** while operating near **privileged CI/CD environments**.

That creates a new security boundary.

A malicious pull request, issue comment, markdown file, commit message, or configuration file may influence an AI agent that has access to repository tokens, workflow runners, secrets, shell tools, or deployment paths.

This repository maps those risks and documents practical engineering defenses for safer agentic software delivery.

---

## Table of Contents

- [Agentic CI/CD Security](#agentic-cicd-security)
  - [Why Agentic CI/CD Security?](#why-agentic-cicd-security)
  - [Table of Contents](#table-of-contents)
  - [Core Threat Model](#core-threat-model)
    - [Untrusted Context Flow](#untrusted-context-flow)
    - [Excessive Token Permissions](#excessive-token-permissions)
    - [Unsafe Tool Execution](#unsafe-tool-execution)
    - [Secret Exposure](#secret-exposure)
    - [Unsafe Output Handling](#unsafe-output-handling)
  - [Repository Structure](#repository-structure)
  - [Checklists](#checklists)
  - [Threat Models](#threat-models)
  - [Examples](#examples)
  - [Resources](#resources)
    - [Initial High-Signal Resources](#initial-high-signal-resources)
  - [Contributing](#contributing)
  - [License](#license)

---

## Core Threat Model

AI agents operating within software delivery pipelines often read untrusted context while operating near privileged environments.

Common untrusted inputs include:

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

Poisoned pull requests, malicious markdown, injected commit messages, or hostile documentation may attempt to manipulate agent behavior.

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
.github/workflows/
  CI workflows for validating the repository itself.

assets/
  Images, banners, diagrams, and visual materials used in the project.

checklists/
  Actionable security checklists for reviewing agentic CI/CD workflows.

examples/
  Vulnerable and hardened workflow examples.

threat-models/
  Threat models for common AI-agent software delivery patterns.

resources/
  Curated tools, standards, papers, blog posts, and case studies.
```

---

## Checklists

The `checklists/` directory contains practical, review-friendly security guidance.

Current checklist:

- [GitHub Actions AI Agent Security Checklist](checklists/github-actions-agent-security.md)

Planned checklist topics include:

- GitLab CI/CD agent security checklist
- Prompt injection review checklist
- Secrets and permissions checklist
- Release safety checklist
- Human approval and review checklist

---

## Threat Models

The `threat-models/` directory contains structured threat models for common AI-agent software delivery use cases.

Current threat model:

- [Pull Request Review Agent Threat Model](threat-models/pr-review-agent.md)

Planned threat models include:

- Issue triage agent
- Coding agent
- Documentation generation agent
- Release automation agent
- Dependency update agent

---

## Examples

The `examples/` directory contains reference implementations showing both insecure and hardened designs.

Current examples:

- [Unsafe PR Agent Review Workflow](examples/vulnerable-workflows/unsafe-pr-agent.yml)
- [Safer PR Agent Review Workflow](examples/hardened-workflows/safe-pr-agent.yml)

Supporting documentation:

- [Vulnerable Workflow Examples](examples/vulnerable-workflows/README.md)
- [Hardened Workflow Examples](examples/hardened-workflows/README.md)

The goal is to make security risks visible through practical workflow examples, not only abstract explanations.

---

## Resources

The `resources/` directory collects high-signal materials related to agentic CI/CD security.

Current resource index:

- [Agentic CI/CD Security Resources](resources/README.md)

Resource categories include:

- Agentic CI/CD security
- Prompt injection and workflow injection
- Defensive tools and frameworks
- Standards and security guidance
- MCP and tool invocation security
- Sandboxing and isolation
- Research papers
- Case studies and industry writeups

### Initial High-Signal Resources

- [Agentic Actions Auditor](https://trailofbits-skills.mintlify.app/plugins/agentic-actions-auditor) — Trail of Bits guidance for auditing GitHub Actions workflows that invoke AI coding agents.
- [mcp-context-protector](https://github.com/trailofbits/mcp-context-protector) — A Trail of Bits security wrapper for MCP-based LLM applications.
- [OWASP Top 10 for Agentic Applications](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/) — OWASP’s emerging risk framework for autonomous and agentic AI systems.
- [Model Context Protocol: Tools Specification](https://modelcontextprotocol.io/specification/2025-06-18/server/tools) — MCP guidance covering tool invocation and human-in-the-loop approval.
- [GitInject: Real-World Prompt Injection Attacks in AI-Powered CI/CD Pipelines](https://arxiv.org/abs/2606.09935) — Research on prompt injection vulnerabilities in real AI-powered CI/CD workflows.

---

## Contributing

Contributions are welcome.

Useful contributions include:

- New checklist items
- Threat models
- Vulnerable workflow examples
- Hardened workflow examples
- Research papers
- Defensive tools
- Case studies
- Corrections to existing guidance
- Better explanations of attack patterns
- Safer CI/CD design patterns

Please keep contributions practical, security-focused, and clearly sourced where possible.

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines.

---

## License

This project is licensed under the MIT License.