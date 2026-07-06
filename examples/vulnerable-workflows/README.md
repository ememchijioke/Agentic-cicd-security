# Vulnerable Workflow Examples

This directory contains intentionally vulnerable examples of AI-agent CI/CD workflows.

These examples are for defensive security education only. They should not be copied into production environments.

## Current Examples

- [Unsafe PR Agent Review](unsafe-pr-agent.yml)

## What This Example Shows

The unsafe pull request review agent demonstrates several risky patterns:

- Use of `pull_request_target` while reading untrusted pull request content
- Broad write permissions
- Access to secrets inside an agent job
- Shell execution influenced by pull request content
- Automatic fix and push behavior
- No human approval gate before repository modification

## Why This Matters

AI-agent workflows may process attacker-controlled content from pull requests, issues, comments, commit messages, or repository files.

If the same workflow also has secrets, write permissions, or deployment access, the agent can become a bridge between untrusted input and privileged CI/CD actions.