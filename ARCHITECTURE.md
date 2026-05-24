# Architecture

This document describes the planned architecture for Swiggy OfficeOS.

## High-Level Flow

```text
Slack / Teams
     |
     v
Integration API
     |
     v
Workflow Orchestrator
     |
     +--> Swiggy Food MCP
     +--> Swiggy Instamart MCP
     +--> Approval Service
     +--> Notification Service
     +--> Audit Service
```

## Main Components

### Web API

The .NET 9 Web API will expose endpoints for authentication, workspace setup, workflow creation, approvals, and integration callbacks.

### Web Dashboard

The Angular dashboard will allow admins to configure workplace details, budgets, team preferences, approval rules, and integration settings.

### Agent Workflow Layer

The AI agent layer will interpret workplace requests and convert them into structured workflows. It will not place orders without confirmation where approval is required.

Example responsibilities:

- Understand user intent
- Ask follow-up questions when needed
- Apply workplace budget rules
- Prepare order or pantry suggestions
- Route final actions through approved MCP tools

### Message Queue

RabbitMQ will handle async jobs such as:

- Order planning
- Pantry basket preparation
- Approval reminders
- Notification delivery
- Audit log processing

### Data Store

PostgreSQL will store durable application data:

- Workplaces
- Users
- Team preferences
- Budget rules
- Workflow records
- Approval records
- Integration metadata

### Cache

Redis will be used for:

- Short-lived workflow state
- Rate-limit coordination
- Session-related temporary data
- Frequently accessed configuration

### Real-Time Updates

SignalR will be used to show live workflow updates in the web dashboard, such as pending approval, approved, preparing basket, and completed.

## Security Model

The system will follow a least-privilege approach:

- OAuth-based authentication
- Scoped access per workplace
- Tenant-level isolation
- Encrypted secrets
- Admin approval for sensitive workflows
- Audit logs for order-related actions
- Clear Swiggy attribution in user-facing flows

## Initial Deployment Plan

The first version can run as a small cloud deployment:

- Web API service
- Angular web frontend
- Managed PostgreSQL
- Managed Redis
- RabbitMQ instance
- Centralized logs and monitoring

The expected early request volume is below 1,000 requests per day.

