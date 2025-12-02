---
name: "agentcore"
displayName: "AWS Bedrock AgentCore"
description: "Build, test, and deploy AI agents using AWS Bedrock AgentCore with local development workflow"
keywords: ["agentcore", "bedrock", "aws", "agents", "ai", "strands", "development", "agent"]
author: "AWS"
---

# AWS Bedrock AgentCore

## Overview

Build and deploy AI agents using AWS Bedrock AgentCore with a complete local development workflow. This power provides access to AgentCore documentation, runtime management, memory operations, and gateway configuration through MCP tools, plus comprehensive guidance for the create-dev-test-deploy cycle.

AgentCore supports multiple agent SDKs (Strands, Claude, OpenAI) and model providers (Bedrock, OpenAI), with infrastructure deployment via CDK or Terraform.

## When to Use This Power

- Creating new AgentCore projects with `agentcore create`
- Starting local development servers with hot reloading
- Testing agents locally before cloud deployment
- Searching AgentCore documentation
- Managing agent runtime, memory, and gateway configurations
- Deploying agents to AWS
- Working with Strands agents framework

## Available MCP Tools

This power provides two MCP servers:

### agentcore-mcp-server
- `search_agentcore_docs` - Search AgentCore documentation
- `fetch_agentcore_doc` - Retrieve specific documentation pages
- `manage_agentcore_runtime` - Manage agent runtime configuration
- `manage_agentcore_memory` - Handle agent memory operations
- `manage_agentcore_gateway` - Configure agent gateway settings

### strands-mcp-server
- `search_docs` - Search Strands framework documentation
- `fetch_doc` - Retrieve Strands documentation pages

## Prerequisites

Before starting with AgentCore:

1. **Install the toolkit:**
   ```bash
   pip install bedrock-agentcore-starter-toolkit
   ```

2. **AWS Authentication:**
   - Use `aws login` to authenticate when using Bedrock as model provider
   - Ensure you have access to the required models in AWS Bedrock

3. **Check model access:**
   - Verify you have permissions for the Bedrock models you plan to use

## Quick Start Workflow

**IMPORTANT:** When creating or starting to build a new agent, always use the `getting-started.md` steering file for detailed step-by-step guidance. Use `readPowerSteering("agentcore", "getting-started.md")` to access the complete workflow guide.

## Integration Guides

### AgentCore Gateway Integration

If you want to integrate AgentCore Gateway into your agent, refer to the gateway integration steering file for detailed instructions on configuration, setup, and best practices. Use `readPowerSteering("agentcore", "agentcore-gateway-integration.md")` to access the guide.

### AgentCore Memory Integration

If you want to add AgentCore Memory to your agent, refer to the memory integration steering file for comprehensive guidance on memory configuration, operations, and implementation patterns. Use `readPowerSteering("agentcore", "agentcore-memory-integration.md")` to access the guide.

## Using MCP Tools

### Search Documentation

To search AgentCore docs:
```
usePower("agentcore", "agentcore-mcp-server", "search_agentcore_docs", {
  "query": "deployment configuration"
})
```

### Fetch Specific Documentation

```
usePower("agentcore", "agentcore-mcp-server", "fetch_agentcore_doc", {
  "doc_id": "getting-started"
})
```

### Search Strands Documentation

```
usePower("agentcore", "strands-mcp-server", "search_docs", {
  "query": "agent memory"
})
```

## Troubleshooting

### Dev Server Won't Start

**Error:** `Could not find entrypoint module`
**Solution:** Ensure `.bedrock_agentcore.yaml` exists or specify entrypoint manually

**Error:** `Port 8080 already in use`
**Solution:** The CLI will automatically try the next available port

### Local Invoke Fails

**Error:** `Connection refused`
**Solution:** Ensure dev server is running with `agentcore dev`

**Error:** `Invalid JSON payload`
**Solution:** Use proper JSON format or plain text (which gets auto-wrapped)

### Deployment Issues

**Error:** `AWS authentication failed`
**Solution:** Run `aws login` to authenticate

**Error:** `Model access denied`
**Solution:** Verify you have permissions for the Bedrock model in AWS console

## Additional Resources

For detailed development workflow guidance, see the steering file which covers:
- Complete project creation options
- Development server configuration
- Testing strategies
- Deployment best practices

Use `readPowerSteering("agentcore", "getting-started")` for the full guide.
