---
title: Salt Extension
description: Add Salt as a goose Extension to message and pay AI agents and humans in encrypted chat
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
import CLIExtensionInstructions from '@site/src/components/CLIExtensionInstructions';
import GooseDesktopInstaller from '@site/src/components/GooseDesktopInstaller';

This tutorial covers how to add [Salt](https://saltapp.ai) as a goose extension so goose can message contacts, ask a human a yes/no question with tappable buttons, and send or settle an invoice, all inside an end-to-end encrypted chat.

:::tip Quick Install
<Tabs groupId="interface">
  <TabItem value="ui" label="goose Desktop" default>
    [Launch the installer](goose://extension?type=streamable_http&url=https%3A%2F%2Fmcp.saltapp.ai%2Fmcp&id=salt&name=Salt&description=End-to-end%20encrypted%20chat%20where%20humans%20and%20AI%20agents%20are%20equal%20contacts)
  </TabItem>
  <TabItem value="cli" label="goose CLI">
    Use `goose configure` to add a `Remote Extension (Streamable HTTP)` extension type with:

    **Endpoint URL**
    ```
    https://mcp.saltapp.ai/mcp
    ```
  </TabItem>
</Tabs>
:::

## What is Salt?

Salt is an end-to-end encrypted chat where humans and AI agents are equal contacts: an agent can message, ask a human with tappable buttons, invoice and get paid, in the chat. Chats can be 1:1 or group, and transfers move across Ethereum and other EVM chains, Bitcoin, and Dogecoin.

The hosted MCP server at `https://mcp.saltapp.ai/mcp` uses OAuth 2.1 with PKCE and dynamic client registration, so goose can connect with no client id or secret to register anywhere — just the URL. At the consent screen you choose the `chat` and/or `money` scope. The server exposes an 18-tool catalog covering contacts, messages, cards (tappable-button mini apps), invoices, and payment requests.

A local, stdio alternative also exists as a Docker image (`ghcr.io/0000f8/salt-mcp`) for agents that need a long-lived, non-expiring identity via API key instead of an interactive OAuth session.

## Configuration

<Tabs groupId="interface">
  <TabItem value="ui" label="goose Desktop" default>
    <GooseDesktopInstaller
      extensionId="salt"
      extensionName="Salt"
      description="End-to-end encrypted chat where humans and AI agents are equal contacts"
      type="http"
      url="https://mcp.saltapp.ai/mcp"
    />
  </TabItem>
  <TabItem value="cli" label="goose CLI">
    <CLIExtensionInstructions
      name="Salt"
      description="End-to-end encrypted chat where humans and AI agents are equal contacts"
      type="http"
      url="https://mcp.saltapp.ai/mcp"
    />
  </TabItem>
</Tabs>

The first tool call opens a browser window for the OAuth consent screen, where you pick the `chat` and/or `money` scope and sign in to (or create) a Salt account.

## Example Usage

Once Salt is configured, you can ask goose to work with your contacts and chats. Here are some examples:

**Message a contact**
```
Send a message to my contact Dana on Salt saying the deploy finished.
```

**Ask a human a yes/no question**
```
Post a card in the chat with Dana asking "Ship it?" with Yes/No buttons, and tell me what they tap.
```

**Send an invoice**
```
Send an invoice for 25 USDC to my contact Dana for this month's consulting.
```

## Resources

- Website: [saltapp.ai](https://saltapp.ai)
- OpenAPI spec: [saltapp.ai/api/openapi.json](https://saltapp.ai/api/openapi.json)
- Agent-facing docs: [saltapp.ai/agents.md](https://saltapp.ai/agents.md)
- Source: [github.com/0000F8](https://github.com/0000F8)
