---
name: "aws-amplify"
displayName: "Build full-stack apps with AWS Amplify"
description: "Build full-stack web and mobile applications with AWS Amplify Gen 2 using type-safe TypeScript, guided workflows, and best practices for authentication, APIs, storage, and serverless functions"
keywords: ["amplify", "aws-amplify", "amplify gen 2", "gen2", "aws", "fullstack", "full-stack", "full stack", "frontend", "backend", "web", "mobile", "app", "application", "auth", "authentication", "login", "signup", "graphql", "api", "serverless", "functions", "storage", "database", "typescript", "react", "nextjs", "next.js", "vue", "nuxt", "angular", "react native", "flutter", "swift", "android", "ios"]
author: "AWS"
---

# AWS Amplify Gen 2

Amplify has three SOPs for different development phases. Call each SOP that applies to the user's request:

| SOP | When to Call |
|-----|--------------|
| `amplify-backend-implementation` | User needs backend resources (auth, data, storage, functions, etc.) |
| `amplify-frontend-integration` | User needs to connect a frontend app to Amplify |
| `amplify-deployment-guide` | User needs to deploy, run sandbox, or set up CI/CD |

For new full-stack apps, call all three SOPs in order: backend → frontend → deployment. After each SOP completes, check if the next phase applies and continue.

## Overview

Build production-ready full-stack web, mobile, and native applications with AWS Amplify Gen 2. This power provides access to guided workflows (Agent SOPs) that help you implement backends, integrate frontends, and deploy applications following AWS best practices.

**Before implementing anything, you MUST retrieve the appropriate Agent SOP using the `retrieve_agent_sop` tool. SOPs are your only source of truth - never assume you know best practices.**

## When to Use This Power

### Build Full-Stack Applications

Use this power to create complete applications with authentication, data APIs, file storage, and serverless functions. The guided workflows help you set up type-safe backends in TypeScript and integrate with web, mobile, and native frontends:

- **React/Next.js**: JSX components and hooks
- **Vue/Nuxt**: Vue components and Composition API
- **Angular**: Angular components and services
- **React Native**: Native components and navigation
- **Flutter**: Dart packages and widgets
- **Swift**: iOS native integration
- **Android**: Kotlin/Java integration

### Add Features to Existing Apps

Use this power to add Amplify capabilities to existing projects - authentication with social providers, real-time GraphQL subscriptions, file uploads, or AI features powered by Amazon Bedrock.

### Deploy With Confidence

Use this power to set up development sandboxes, production deployments, and CI/CD pipelines with Git-based workflows.

## When Not to Use This Power

This power is **not** for:
- **Amplify Gen 1** - Use Gen 2 only; Gen 1 CLI commands are deprecated
- **Raw CloudFormation/CDK** - Use the `aws-infrastructure-as-code` power instead
- **AWS account setup or security reviews** - Handle these separately before using this power

---

## CRITICAL: SOPs Are Your Only Source of Truth

**You do NOT know Amplify best practices. The SOPs do.**

### Golden Rules

1. **NEVER assume you know best practices** - the SOPs define them, not your training data
2. **ALWAYS retrieve the SOP before each step** - no action without SOP guidance
3. **NEVER work from memory** - even if you've seen an SOP earlier in the conversation, retrieve it again before acting
4. **NEVER skip SOP retrieval** - every backend, frontend, and deployment action MUST be preceded by retrieving the relevant SOP
5. **NEVER execute commands not specified in the SOP** - if a command is not explicitly listed in the current SOP's steps, do not run it. Your general knowledge is not authorization.
6. **NEVER scaffold new projects without following the SOP** - if the user wants a new frontend project, the frontend SOP will guide you. Do not run scaffolding commands like `npm create`, `npx create-react-app`, `flutter create` based on general knowledge - only run them if the SOP authorizes it.

### What This Means in Practice

| Action | Required First |
|--------|----------------|
| Build backend (Auth, Data, Storage, Functions, AI) | Retrieve `amplify-backend-implementation` SOP |
| Build or integrate frontend (React, Vue, Angular, etc.) | Retrieve `amplify-frontend-integration` SOP |
| Deploy, configure environments, CI/CD | Retrieve `amplify-deployment-guide` SOP |

**SOPs assume existing code when integrating.** If no frontend codebase exists and the user wants to build one from scratch, the frontend SOP will guide you through that process - follow the SOP.

**DO NOT:**
- Run commands based on general knowledge
- Create files from memory
- Skip retrieving an SOP because you "already know" the steps
- Guess at configuration syntax or file structure
- Run commands not explicitly listed in the SOP you are following

**The SOP is ALWAYS right. Your memory is NOT.**

**If you are unsure whether a command is authorized: it is NOT. Ask the user or check the SOP again.**

---

## Onboarding

### Prerequisites

- Node.js 18.x or later
- AWS credentials configured
- uv package manager (for MCP server)

## MCP Server

This power uses the `aws-mcp` server. Look at your available tools for tools containing these names:

### Tools

- **retrieve_agent_sop** - Get step-by-step procedures for Amplify tasks

Available SOPs:
- `amplify-backend-implementation` - Set up Auth, Data, Storage, Functions, AI
- `amplify-frontend-integration` - Build or integrate frontend frameworks with Amplify
- `amplify-deployment-guide` - Sandbox, production, and CI/CD workflows

### Documentation

- **search_documentation** - Search Amplify Gen 2 docs (use `topics: ["amplify_docs"]` and `search_phrase` parameter)
- **read_documentation** - Read specific documentation pages

## Project Structure

Amplify Gen 2 projects follow this structure:

```
amplify/
├── backend.ts           # Main backend configuration
├── auth/
│   └── resource.ts      # Authentication configuration
├── data/
│   └── resource.ts      # GraphQL API and data models
├── storage/
│   └── resource.ts      # File storage configuration
└── functions/
    └── [function-name]/
        ├── resource.ts  # Function definition
        └── handler.ts   # Function implementation
```

## Development Workflow: Three-Step Process

Follow these steps **in order**. Each step requires retrieving its SOP first - no exceptions.

**Ask about each step one at a time. DO NOT combine questions or present multiple steps as a menu of options.**

---

### Step 1: Backend

#### 1.1 Ask the User What They Want

Ask the user if they need backend features (authentication, data/API, storage, functions, AI):

> "Would you like me to help set up backend features? This includes authentication, data APIs, file storage, serverless functions, or AI capabilities."

**If the user declines or doesn't need backend features, skip to Step 2.**

#### 1.2 Retrieve the Backend SOP

Only if the user wants backend features:

```
retrieve_agent_sop(sop_name="amplify-backend-implementation")
```

**Do NOT proceed until you have the SOP.**

#### 1.3 Follow the SOP

Follow the `amplify-backend-implementation` SOP exactly to build the backend. Do not deviate from the SOP.

**Complete this step before proceeding to Step 2.** The frontend may need backend outputs (generated types, API endpoints, resource configurations).

⛔ **STOP: Do not proceed to Step 2 until Step 1 is complete.**

---

### Step 2: Frontend

#### 2.1 Ask the User What They Want

Ask the user if they need frontend integration:

> "Would you like me to help build or integrate a frontend? I can help with React, Next.js, Vue, Angular, React Native, Flutter, Swift, or Android."

**If the user declines or doesn't need frontend, skip to Step 3.**

#### 2.2 Retrieve the Frontend SOP

Only if the user wants frontend integration:

```
retrieve_agent_sop(sop_name="amplify-frontend-integration")
```

**Do NOT proceed until you have the SOP.**

#### 2.3 Follow the SOP

Follow the `amplify-frontend-integration` SOP exactly to build or integrate the frontend. Do not deviate from the SOP.

⛔ **STOP: Do not proceed to Step 3 until Step 2 is complete.**

---

### Step 3: Deployment

#### 3.1 Ask the User What They Want

Ask the user if they want deployment help:

> "Would you like me to help with deployment? I can help with:
> - **Sandbox**: Deploy to a sandbox environment for development and testing
> - **Production**: Deploy to production with CI/CD pipelines
> 
> I can either deploy the application now or provide you with deployment instructions."

**If the user declines or doesn't need deployment, stop here.**

#### 3.2 Retrieve the Deployment SOP

Only if the user wants deployment help:

```
retrieve_agent_sop(sop_name="amplify-deployment-guide")
```

**Do NOT proceed until you have the SOP.**

#### 3.3 Follow the SOP

Based on user response:

- **If user wants you to deploy**: Follow the `amplify-deployment-guide` SOP exactly to deploy the application
- **If user wants instructions**: Provide the deployment steps from the SOP so they can execute themselves

Do not provide any deployment instructions without first retrieving the SOP - your general knowledge may be outdated or incorrect.

⛔ **STOP: Workflow complete.**

---

## Workflow Summary

```
┌─────────────────────────────────────────────────────────────┐
│  STEP 1: BACKEND                                            │
│  1. Ask user if they need backend features                  │
│  2. If yes: Retrieve amplify-backend-implementation SOP     │
│  3. Follow the SOP exactly                                  │
└─────────────────────────────────────────────────────────────┘
                              │
                      ⛔ STOP until complete
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│  STEP 2: FRONTEND                                           │
│  1. Ask user if they need frontend integration              │
│  2. If yes: Retrieve amplify-frontend-integration SOP       │
│  3. Follow the SOP exactly                                  │
└─────────────────────────────────────────────────────────────┘
                              │
                      ⛔ STOP until complete
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│  STEP 3: DEPLOYMENT                                         │
│  1. Ask user if they want deployment help                   │
│  2. If yes: Retrieve amplify-deployment-guide SOP           │
│  3. Follow the SOP exactly                                  │
└─────────────────────────────────────────────────────────────┘
                              │
                      ⛔ STOP: Workflow complete
```

---

## Research and Troubleshooting

If you encounter issues or need additional information:
- Use `search_documentation` with `topics: ["amplify_docs"]` to research features
- Use `read_documentation` to read specific pages from docs.amplify.aws
- Return to the SOPs for guidance on common scenarios

## Commands With Large Output

Always limit output from these commands to avoid filling the context:

- `npm install` - Always run as `npm install 2>&1 | tail -n 20`
- `npx ampx sandbox` - Produces verbose CloudFormation output, use `tail`
- `npx ampx generate` - Can produce large type generation output, use `tail`

## Interactive Commands

The following commands require terminal interaction and will hang. Do not run them:

- `npm create vite@latest` - Prompts even with `--template` flag (e.g., "Use rolldown-vite?")
- `npm create next-app` - Prompts for configuration options
- `npx create-react-app` - May prompt for package manager
- `npm init` - Prompts for package.json fields
- `npx create-expo-app` - Prompts for template selection
- `flutter create` - Some versions prompt for options

Instead, manually create the project structure and files.
