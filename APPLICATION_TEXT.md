# Application Text

Use this file to copy and paste into the Swiggy Builders Club application.

## Team / Project Name

Swiggy OfficeOS

## What Are You Building?

Swiggy OfficeOS is an AI-powered workplace food and pantry copilot for Indian teams and offices.

It integrates with Slack and Microsoft Teams, using Swiggy Food and Swiggy Instamart MCP servers to automate common workplace workflows such as team meal coordination, pantry restocking, deployment-night ordering, budget-aware group ordering, and recurring office supplies planning.

The goal is to reduce operational friction for office admins, founders, HR teams, and engineering teams while creating useful, high-intent workplace commerce workflows through contextual AI automation.

This is not meant to hide or replace Swiggy's user experience. The product acts as a workplace productivity layer that helps teams plan and coordinate recurring food and pantry needs while routing approved actions through Swiggy MCP.

## Which MCP Servers Do You Need?

Swiggy Food

Swiggy Instamart

## What Type Of Integration Is This?

AI Agent / Copilot

Web App

Slack / Microsoft Teams Bot

## Tech Stack And Architecture Overview

The platform is being built using .NET 9 Web API, Angular, PostgreSQL, Redis, RabbitMQ, and SignalR. AI orchestration is handled through an agent-based workflow layer using OpenAI-compatible tooling and MCP integrations.

Slack and Teams integrations will trigger contextual workplace workflows such as team meal planning, pantry replenishment, deployment-night ordering automation, and budget-aware group ordering.

The architecture is event-driven and modular. RabbitMQ will handle async workflow execution, Redis will support caching and temporary workflow state, PostgreSQL will store workplace data and audit records, and SignalR will provide real-time workflow status updates.

Authentication will use secure OAuth-based flows with scoped permissions, tenant-level isolation, centralized logging, and audit trails for sensitive actions.

## Redirect URIs

```text
http://localhost:4200/auth/callback
http://localhost:5000/auth/callback
https://getofficeos.com/auth/callback
```

## Expected Request Volume

Below 1,000 requests per day during the initial MVP and pilot phase.

## Demo Link, GitHub Repo, Or Anything Else

I am currently building the MVP for Swiggy OfficeOS, focused on AI-assisted deployment-night ordering and workplace pantry automation workflows.

The first version will include a Slack-based ordering assistant, pantry restocking suggestions through Instamart, budget-aware group ordering, admin approval flows, and basic audit history for workplace orders.

The project is in the early build stage, but the architecture, use cases, and MVP roadmap are already defined.

GitHub: [paste your repo link here]

Portfolio: [paste your portfolio link here]

## Security And Privacy Declaration

Swiggy OfficeOS will only request the minimum required scopes for each workflow. Workplace data will be handled with tenant-level isolation, encrypted secrets, audit logs, and role-based access controls.

Transaction data from Swiggy MCP will only be used for approved workplace workflows. The product will not scrape, resell, benchmark, or extract Swiggy data outside the agreed integration scope.

Swiggy attribution will remain visible in user-facing workflows so users understand when they are interacting with Swiggy-powered services.

