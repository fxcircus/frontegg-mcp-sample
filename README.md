# Frontegg MCP Integration Setup

This repository demonstrates how to set up and use the Frontegg Management Control Panel (MCP) integration with Cursor AI. It implements the [Frontegg MCP Server](https://github.com/frontegg/frontegg-mcp-server) which allows you to interact with Frontegg's API directly from your IDE.

## Table of Contents
- [Setup Instructions](#setup-instructions)
- [Enabling MCP in Cursor](#enabling-mcp-in-cursor)
- [Features](#features)
  - [Available Tools](#available-tools)
    - [Roles Management](#roles-management)
    - [Permissions Management](#permissions-management)
    - [User Management](#user-management)
    - [Application Management](#application-management)
    - [Tenant Management](#tenant-management)
    - [Token Management](#token-management)
    - [Vendor Integration](#vendor-integration)
- [Troubleshooting](#troubleshooting)

## Setup Instructions

1. Initialize a new Node.js project:
   ```bash
   npm init -y
   ```

2. Install the Frontegg MCP server:
   ```bash
   npm i @frontegg/frontegg-mcp-server
   ```

3. Create the `.cursor` directory and MCP configuration file (if they don't exist already):
   ```bash
   mkdir -p .cursor && touch .cursor/mcp.json
   ```

4. Add the following configuration to `.cursor/mcp.json` (replace with your Frontegg credentials):
   ```json
   {
       "mcpServers": {
         "frontegg": {
           "command": "node",
           "args": ["./node_modules/@frontegg/frontegg-mcp-server/build/index.js"],
           "env": {
             "FRONTEGG_CLIENT_ID": "your_client_id_here",
             "FRONTEGG_API_KEY": "your_api_key_here"
           }
         }
       }
     }
   ```

5. Save the file.

## Enabling MCP in Cursor

1. Open Cursor settings from the ⚙️ icon ➜ click on `MCP` ➜ Enable the MCP server agent.

2. Close all Cursor windows completely and re-open them.

3. Open Cursor AI chat (`⌥ + ⌘ + B`), select the Frontegg agent from the dropdown, and ask it a question like "get frontegg roles on my account".

## Features

With this integration, you can:
- Manage Frontegg roles and permissions
- Query user information
- Perform other Frontegg administrative tasks directly from Cursor AI

### Available Tools

#### Roles Management
- Get roles
- Create role
- Delete role
- Update role
- Set permissions to role

#### Permissions Management
- Get permissions
- Create permission
- Delete permission
- Update permission
- Set permission to multiple roles
- Set permissions classification
- Get permission categories
- Create permission category
- Update permission category
- Delete permission category

#### User Management
- Get users
- Invite user
- Delete user
- Update user
- Get users for application
- Assign users to application

#### Application Management
- Get applications
- Get agent applications
- Create agent application
- Update agent application

#### Tenant Management
- Create tenant
- Delete tenant
- Update tenant

#### Token Management
- Create token
- Get tokens
- Delete token
- Get client credentials
- Create client credentials
- Update client credentials
- Delete client credentials

#### Vendor Integration
- Get vendor integrations
- Create vendor integration
- Update vendor integration
- Delete vendor integration
- Assign agents to vendor integration
- Unassign agents from vendor integration
- Get Frontegg integrations
- Get Frontegg integration

## Troubleshooting

If you encounter issues:
- Ensure your Frontegg credentials are correct
- Verify that you've restarted Cursor completely after enabling MCP
- Check that you've selected the correct agent in the Cursor AI chat dropdown 