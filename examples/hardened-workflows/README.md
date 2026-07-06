# Hardened Workflow Examples

This directory contains safer reference patterns for AI-agent CI/CD workflows.

These examples are not universal templates, but they show design patterns that reduce common risks.

## Current Examples

- [Safer PR Agent Review](safe-pr-agent.yml)

## What This Example Shows

The safer pull request review agent demonstrates several defensive patterns:

- Use of `pull_request` for untrusted pull request analysis
- Read-only repository permissions
- No secrets exposed to the agent job
- No deployment credentials
- No direct push behavior
- Generated report uploaded as an artifact
- Human review before merge, release, or deployment

## Safer Design Principle

A safer AI-agent CI/CD workflow should generally follow this pattern:

```text
Untrusted input
    ↓
Read-only agent analysis
    ↓
Generated report or suggestion
    ↓
Security checks
    ↓
Human review
    ↓
Separate trusted merge or deployment workflow