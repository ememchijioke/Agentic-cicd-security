# Resources

This directory collects high-signal resources for understanding and securing AI agents in CI/CD pipelines, GitHub Actions, GitLab workflows, and autonomous software delivery environments.

The goal is to keep this list practical, security-focused, and useful for engineers reviewing agentic CI/CD workflows.

---

## Resource Categories

- [Resources](#resources)
  - [Resource Categories](#resource-categories)
  - [Agentic CI/CD Security](#agentic-cicd-security)
  - [Prompt Injection and Workflow Injection](#prompt-injection-and-workflow-injection)
  - [Defensive Tools and Frameworks](#defensive-tools-and-frameworks)
  - [Standards and Security Guidance](#standards-and-security-guidance)
  - [MCP and Tool Invocation Security](#mcp-and-tool-invocation-security)
  - [Sandboxing and Isolation](#sandboxing-and-isolation)
  - [Research Papers](#research-papers)
  - [Case Studies and Industry Writeups](#case-studies-and-industry-writeups)
  - [Contribution Guidelines](#contribution-guidelines)

---

## Agentic CI/CD Security

Resources focused specifically on AI agents operating inside CI/CD pipelines, repository automation, pull request workflows, and software delivery environments.

- [GitHub Agentic Workflows](https://github.github.com/gh-aw/) — GitHub and Microsoft documentation for agentic workflows in GitHub Actions, including security-first design concepts such as guardrails, sandboxed execution, and safe outputs.
- [Securing CI/CD in an Agentic World: Claude Code GitHub Action Case](https://www.microsoft.com/en-us/security/blog/2026/06/05/securing-ci-cd-in-agentic-world-claude-code-github-action-case/) — Microsoft security analysis of AI-agent risks in GitHub Actions and CI/CD environments.
- [AI Agent Prompt Injection: The New CI/CD Supply Chain Attack](https://labs.cloudsecurityalliance.org/research/csa-research-note-claude-code-github-action-prompt-injection/) — Cloud Security Alliance research note on prompt injection risks in AI-powered CI/CD workflows.
- [Prompt Injection in AI-Powered GitHub Actions](https://labs.cloudsecurityalliance.org/research/csa-research-note-ai-github-actions-security-20260503-csa-st/) — Cloud Security Alliance research note on how AI agents change the CI/CD threat model.

---

## Prompt Injection and Workflow Injection

Resources explaining how untrusted text can influence AI agents, workflows, tool calls, or downstream automation.

- [Demystifying and Detecting Agentic Workflow Injection Vulnerabilities in GitHub Actions](https://arxiv.org/abs/2605.07135) — Research paper introducing Agentic Workflow Injection in GitHub Actions and describing Prompt-to-Agent and Prompt-to-Script patterns.
- [GitInject: Real-World Prompt Injection Attacks in AI-Powered CI/CD Pipelines](https://arxiv.org/abs/2606.09935) — Research paper and framework for evaluating prompt injection vulnerabilities in real GitHub workflows.
- [How Agentic AI Coding Assistants Become the Attacker's Shell](https://arxiv.org/abs/2605.25871) — Research on how hidden instructions in external artifacts can hijack coding agents into executing unauthorized commands.
- ["Your AI, My Shell": Demystifying Prompt Injection Attacks on Agentic AI Coding Editors](https://arxiv.org/abs/2509.22040) — Research on prompt injection attacks against high-privilege coding editors and agentic development environments.

---

## Defensive Tools and Frameworks

Tools and frameworks that can support review, hardening, or security analysis of agentic workflows.

- [Agentic Actions Auditor](https://trailofbits-skills.mintlify.app/plugins/agentic-actions-auditor) — Trail of Bits guidance for auditing GitHub Actions workflows that invoke AI coding agents.
- [Trail of Bits Skills Marketplace](https://github.com/trailofbits/skills) — Security-focused Claude Code skills, including agentic workflow auditing support.
- [mcp-context-protector](https://github.com/trailofbits/mcp-context-protector) — A Trail of Bits security wrapper for protecting MCP-based LLM applications from unauthorized actions.
- [AI Red Teaming Guide](https://github.com/requie/AI-Red-Teaming-Guide) — A broader AI red teaming resource that can help with adversarial testing of agentic systems.

---

## Standards and Security Guidance

Standards, frameworks, and guidance relevant to agentic AI security and secure AI adoption.

- [OWASP Top 10 for Agentic Applications 2026](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/) — OWASP’s risk framework for autonomous and agentic AI systems.
- [OWASP GenAI Security Project](https://genai.owasp.org/) — OWASP project covering LLM, GenAI, agentic application security, governance, red teaming, and secure adoption.
- [OWASP Agentic Skills Top 10](https://owasp.org/www-project-agentic-skills-top-10/) — OWASP project focused on risks and controls around agentic skills and AI tool use.

---

## MCP and Tool Invocation Security

Resources related to Model Context Protocol, tool invocation, and human-in-the-loop approval.

- [Model Context Protocol: Tools Specification](https://modelcontextprotocol.io/specification/2025-06-18/server/tools) — Official MCP tools specification, including guidance around human-in-the-loop approval and visibility into tool invocation.
- [Model Context Protocol: Latest Tools Specification](https://modelcontextprotocol.io/specification/2025-11-25/server/tools) — Later MCP tools specification with similar trust and safety guidance for tool use.
- [Model Context Protocol Security](https://github.com/cosai-oasis/ws4-secure-design-agentic-systems/blob/main/model-context-protocol-security.md) — Security design guidance for MCP, including risks around consent fatigue and tool approval.
- [MCP Security Best Practices](https://obot.ai/resources/learning-center/mcp-security/) — Practical guidance on authentication, least privilege, logging, and human-in-the-loop controls for MCP-based systems.

---

## Sandboxing and Isolation

Resources relevant to isolating AI-agent execution environments and reducing blast radius.

- [GitHub Agentic Workflows](https://github.github.com/gh-aw/) — Includes design concepts around sandboxed execution and safe outputs for agentic workflows.
- [Model Context Protocol: Tools Specification](https://modelcontextprotocol.io/specification/2025-06-18/server/tools) — Relevant for tool exposure, user approval, and safer tool invocation design.
- [mcp-context-protector](https://github.com/trailofbits/mcp-context-protector) — Useful as a defensive layer around MCP-based tool access.

Planned additions:

- Container isolation references
- GitHub Actions permission hardening references
- GitLab CI/CD isolation references
- Network egress restriction patterns
- Ephemeral runner security references

---

## Research Papers

Academic and technical research directly relevant to agentic CI/CD security.

- [Demystifying and Detecting Agentic Workflow Injection Vulnerabilities in GitHub Actions](https://arxiv.org/abs/2605.07135) — Introduces Agentic Workflow Injection and reports large-scale analysis of real-world agentic GitHub Actions workflows.
- [GitInject: Real-World Prompt Injection Attacks in AI-Powered CI/CD Pipelines](https://arxiv.org/abs/2606.09935) — Studies real workflow configurations and attack classes against AI-powered CI/CD pipelines.
- [How Agentic AI Coding Assistants Become the Attacker's Shell](https://arxiv.org/abs/2605.25871) — Examines prompt-injection attacks where external artifacts hijack agentic coding assistants.
- ["Your AI, My Shell": Demystifying Prompt Injection Attacks on Agentic AI Coding Editors](https://arxiv.org/abs/2509.22040) — Studies prompt injection against high-privilege agentic coding editors.

---

## Case Studies and Industry Writeups

Real-world or industry-facing writeups that help explain practical risks.

- [Securing CI/CD in an Agentic World: Claude Code GitHub Action Case](https://www.microsoft.com/en-us/security/blog/2026/06/05/securing-ci-cd-in-agentic-world-claude-code-github-action-case/) — Microsoft writeup on AI-agent security risks in CI/CD.
- [AI Agent Prompt Injection: The New CI/CD Supply Chain Attack](https://labs.cloudsecurityalliance.org/research/csa-research-note-claude-code-github-action-prompt-injection/) — CSA analysis of prompt injection as a CI/CD supply-chain issue.
- [Prompt Injection in AI-Powered GitHub Actions](https://labs.cloudsecurityalliance.org/research/csa-research-note-ai-github-actions-security-20260503-csa-st/) — CSA writeup on prompt injection in AI-powered GitHub Actions.
- [Agentic coding tools can be exploited by trying to be helpful](https://www.techradar.com/pro/security/agentic-coding-tools-have-access-to-everything-they-need-for-this-security-experts-warn-claude-code-can-be-exploited-simply-by-trying-to-be-helpful) — News coverage of agentic coding tool exploitation via malicious instructions.
- [Anthropic's official Git MCP server security flaws](https://www.techradar.com/pro/security/anthropics-official-git-mCP-server-had-some-worrying-security-flaws-this-is-what-happened-next) — Coverage of Git MCP server vulnerabilities and agentic integration risks.

---

## Contribution Guidelines

When adding a resource, use this format:

```markdown
- [Resource Name](https://example.com) — Short explanation of why this resource is useful.