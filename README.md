# Swiggy OfficeOS

Swiggy OfficeOS is an early-stage idea for an AI-powered workplace food and pantry copilot for Indian teams.

The product is designed to help offices handle the small but frequent food-related workflows that usually create friction during the workday: team lunches, late-night deployment meals, pantry restocking, budget approvals, and recurring office supply planning.

The goal is simple: make workplace ordering feel less manual, more organized, and more useful without hiding the Swiggy experience or confusing users about where the service comes from.

## Why This Exists

In many teams, food and pantry coordination still happens through scattered Slack messages, spreadsheets, WhatsApp groups, and one person manually collecting preferences.

That works for small moments, but it gets messy when teams grow or when ordering becomes recurring:

- Who is ordering today?
- What is the budget?
- Who is vegetarian?
- Does the office need snacks, drinks, or basic pantry items?
- Who approved the order?
- Was this a one-time meal or a recurring workflow?

Swiggy OfficeOS explores how AI agents and MCP-based integrations can turn these repeated workplace tasks into structured, secure, and auditable workflows.

## What It Will Do

The initial MVP is focused on practical office workflows:

- Slack or Microsoft Teams assistant for team meal planning
- Deployment-night food ordering workflow for engineering teams
- Pantry restocking using Swiggy Instamart
- Budget-aware group ordering
- Admin approval before placing workplace orders
- Team preference collection
- Real-time workflow status updates
- Basic audit history for orders and approvals

The first version is intentionally focused on Food and Instamart use cases. Dineout and broader discovery flows can come later if the core workplace workflows prove useful.

## Example Workflows

### Deployment-Night Ordering

An engineering lead types:

```text
Order dinner for the backend team tonight under Rs 350 per person.
```

The assistant checks team size, preferences, budget rules, and eligible options through Swiggy Food MCP. It then prepares an order plan, asks for approval, and helps complete the workflow.

### Pantry Refill

An office admin types:

```text
Restock the pantry for tomorrow morning.
```

The assistant checks the office pantry profile, previous restock patterns, and available Instamart items. It suggests a basket with tea, coffee, snacks, milk, paper cups, and other recurring items.

### Team Lunch

A manager types:

```text
Plan lunch for 12 people near the office. Keep it simple and vegetarian-friendly.
```

The assistant collects constraints, suggests options, keeps the Swiggy brand visible, and routes the final ordering step through approved MCP flows.

## MCP Servers Needed

- Swiggy Food
- Swiggy Instamart

## Integration Type

- AI Agent / Copilot
- Web App
- Slack / Microsoft Teams Bot

## Planned Tech Stack

- .NET 9 Web API
- Angular
- PostgreSQL
- Redis
- RabbitMQ
- SignalR
- OpenAI-compatible agent orchestration
- Swiggy Food MCP
- Swiggy Instamart MCP

## Architecture Overview

The backend will use a modular, event-driven architecture.

Slack and Teams events will trigger workplace workflows such as meal planning, pantry replenishment, approval requests, and order status updates. These workflows will be handled asynchronously through RabbitMQ, with Redis used for caching, temporary state, and rate-limit coordination.

PostgreSQL will store workplace profiles, team preferences, budget rules, workflow history, approval records, and integration metadata. SignalR will support real-time status updates in the web dashboard.

Authentication will be based on secure OAuth flows, scoped permissions, tenant-level data isolation, and centralized audit logging.

## Security And Privacy Principles

This project is being designed with a conservative data model.

- Request only the minimum required scopes
- Keep Swiggy attribution visible to users
- Store secrets securely
- Maintain tenant-level isolation between workplaces
- Keep audit logs for sensitive workflows
- Avoid scraping, benchmarking, or extracting data outside approved MCP use cases
- Use transaction and ordering data only for the approved workplace workflows

## Current Status

This is currently in the planning and early MVP stage.

The first build will focus on:

- Slack-based deployment-night ordering
- Pantry restocking workflow
- Admin approval flow
- Basic workplace profile setup
- Secure MCP integration proof of concept

## Roadmap

### Phase 1: MVP

- Workplace setup
- Slack command flow
- Team meal planning
- Pantry restock suggestions
- Admin approval
- Basic audit log

### Phase 2: Pilot

- Microsoft Teams support
- Budget policy rules
- Recurring order templates
- Improved team preferences
- Real-time dashboard

### Phase 3: Scale

- Multi-office support
- Usage analytics
- Advanced approval policies
- Enterprise admin controls
- SLA and monitoring improvements

## Application Summary

Swiggy OfficeOS is not meant to replace Swiggy's user experience. It is meant to become a workplace productivity layer that helps teams coordinate recurring food and pantry workflows while routing commerce through approved Swiggy MCP integrations.

The idea is grounded in everyday office operations, not speculative AI. The AI layer exists to reduce coordination work, understand context, and help teams complete useful workflows safely.

