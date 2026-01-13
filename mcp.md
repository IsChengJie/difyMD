# Using MCP Tools

Connect external tools from [MCP servers](https://modelcontextprotocol.io/introduction) to your Dify apps. Instead of just built-in tools, you can use tools from the growing [MCP ecosystem](https://mcpservers.org/).

<Note>
  This covers using MCP tools in Dify. To publish Dify apps as MCP servers, see [here](/en/use-dify/publish/publish-mcp).
</Note>

<Info>
  Only supports MCP servers with [HTTP transport](https://modelcontextprotocol.io/docs/concepts/architecture#transport-layer) right now.
</Info>

## Adding MCP servers

Go to **Tools** → **MCP** in your workspace.

<img src="https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/6cef1436fcc13a65ccedb54bcf5ab77eb87b8faba1098a85951839fb1907f2d2.png?fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=65d4b39cec4a998480db2c8a1ed36831" alt="" data-og-width="3048" width="3048" data-og-height="1988" height="1988" data-path="images/6cef1436fcc13a65ccedb54bcf5ab77eb87b8faba1098a85951839fb1907f2d2.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/6cef1436fcc13a65ccedb54bcf5ab77eb87b8faba1098a85951839fb1907f2d2.png?w=280&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=c4e07c417db39bb1395a1d2fadf9a9d9 280w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/6cef1436fcc13a65ccedb54bcf5ab77eb87b8faba1098a85951839fb1907f2d2.png?w=560&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=09fd00750e22ed7432355566f940e221 560w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/6cef1436fcc13a65ccedb54bcf5ab77eb87b8faba1098a85951839fb1907f2d2.png?w=840&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=80399f660ddafb8c708852e425371cdf 840w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/6cef1436fcc13a65ccedb54bcf5ab77eb87b8faba1098a85951839fb1907f2d2.png?w=1100&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=c76a6d0a048245f829ef2301dc7ba2d3 1100w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/6cef1436fcc13a65ccedb54bcf5ab77eb87b8faba1098a85951839fb1907f2d2.png?w=1650&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=f8d8795253a00d951ddb014217303b59 1650w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/6cef1436fcc13a65ccedb54bcf5ab77eb87b8faba1098a85951839fb1907f2d2.png?w=2500&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=3451f1d020257b2b0a8f69bbdcf06367 2500w" />

Click **Add MCP Server (HTTP)**:

<img src="https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/b5429131836c1caae84f4ce8b3b806221e39636723644961ce2f2a97d5421f16.png?fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=dca573eca5488cc2b52f6e30eefb8dac" alt="" data-og-width="1120" width="1120" data-og-height="912" height="912" data-path="images/b5429131836c1caae84f4ce8b3b806221e39636723644961ce2f2a97d5421f16.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/b5429131836c1caae84f4ce8b3b806221e39636723644961ce2f2a97d5421f16.png?w=280&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=e18bc7b127110017510fe6fbc5ed4d7a 280w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/b5429131836c1caae84f4ce8b3b806221e39636723644961ce2f2a97d5421f16.png?w=560&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=ba0d265c7f17ce0748b1e9e4bf5cdb63 560w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/b5429131836c1caae84f4ce8b3b806221e39636723644961ce2f2a97d5421f16.png?w=840&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=e8e83a6949bca0dc8bbd0a0178eae9f7 840w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/b5429131836c1caae84f4ce8b3b806221e39636723644961ce2f2a97d5421f16.png?w=1100&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=1a66251fe235f30d38ca6d096aab4183 1100w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/b5429131836c1caae84f4ce8b3b806221e39636723644961ce2f2a97d5421f16.png?w=1650&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=f1a51f0f741191d9e797d2b5103e9500 1650w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/b5429131836c1caae84f4ce8b3b806221e39636723644961ce2f2a97d5421f16.png?w=2500&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=9059fc725354528ae78cd91a8ea0a83b 2500w" />

**Server URL**: Where the MCP server lives (like `https://api.notion.com/mcp`)

**Name & Icon**: Call it something useful. Dify tries to grab icons automatically.

**Server ID**: Unique identifier (lowercase, numbers, underscores, hyphens, max 24 chars)

<Warning>
  Never change the server ID once you start using it. This will break any apps that use tools from this server.
</Warning>

## What happens next

Dify automatically:

1. Connects to the server
2. Handles any OAuth stuff
3. Gets the list of available tools
4. Makes them available in your app builder

You'll see a server card once it finds tools:

<img src="https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/fcef5ecad1deca82a1d8988c4bcb7cec745a0cd47945ff05fca588502cfaafbc.png?fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=ff64850c089ed5b06b64449f681f5e69" alt="" data-og-width="1564" width="1564" data-og-height="550" height="550" data-path="images/fcef5ecad1deca82a1d8988c4bcb7cec745a0cd47945ff05fca588502cfaafbc.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/fcef5ecad1deca82a1d8988c4bcb7cec745a0cd47945ff05fca588502cfaafbc.png?w=280&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=8ed17f21e927815caccfce7930a3c6ca 280w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/fcef5ecad1deca82a1d8988c4bcb7cec745a0cd47945ff05fca588502cfaafbc.png?w=560&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=a328ab185ba46e5b525c3189f0222046 560w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/fcef5ecad1deca82a1d8988c4bcb7cec745a0cd47945ff05fca588502cfaafbc.png?w=840&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=69a5c6a0a8e6768a2f95a670a6f1a750 840w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/fcef5ecad1deca82a1d8988c4bcb7cec745a0cd47945ff05fca588502cfaafbc.png?w=1100&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=647cc1d4d01f4444ad9b724ec27ad6fd 1100w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/fcef5ecad1deca82a1d8988c4bcb7cec745a0cd47945ff05fca588502cfaafbc.png?w=1650&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=aa1abe04aaf40e5bcc091bec2e5dbe3f 1650w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/fcef5ecad1deca82a1d8988c4bcb7cec745a0cd47945ff05fca588502cfaafbc.png?w=2500&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=994777c21307bd1d0783461808748504 2500w" />

## Managing servers

Click any server card to:

**Update Tools**: Refresh when the external service adds new tools

<img src="https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/7b526a64ff34b10a357511b2cd3e42f251a6786210eac71c58ca7bfccdf63f0c.png?fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=79785739094935dd3e0fd18c3975de33" alt="" data-og-width="916" width="916" data-og-height="942" height="942" data-path="images/7b526a64ff34b10a357511b2cd3e42f251a6786210eac71c58ca7bfccdf63f0c.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/7b526a64ff34b10a357511b2cd3e42f251a6786210eac71c58ca7bfccdf63f0c.png?w=280&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=948b3f759caf90942c2dd0e7085060ba 280w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/7b526a64ff34b10a357511b2cd3e42f251a6786210eac71c58ca7bfccdf63f0c.png?w=560&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=c6409bdcf5890a4c54ea4d6da5267500 560w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/7b526a64ff34b10a357511b2cd3e42f251a6786210eac71c58ca7bfccdf63f0c.png?w=840&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=d9b0f4c03d05c5ad5ab5fb102deb3b74 840w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/7b526a64ff34b10a357511b2cd3e42f251a6786210eac71c58ca7bfccdf63f0c.png?w=1100&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=711306e1acfe802c28b14518614e977d 1100w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/7b526a64ff34b10a357511b2cd3e42f251a6786210eac71c58ca7bfccdf63f0c.png?w=1650&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=154b69d2ee313380d7da24b2ac61c574 1650w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/7b526a64ff34b10a357511b2cd3e42f251a6786210eac71c58ca7bfccdf63f0c.png?w=2500&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=34870307be56e14c4d808d7deebf1434 2500w" />

**Re-authorize**: Fix auth when tokens expire

**Edit Settings**: Change server details (but not the ID!)

**Remove**: Disconnect the server (this breaks apps using its tools)

## Using MCP tools

Once connected, MCP tools show up everywhere you'd expect:

**In agents**: Tools appear grouped by server ("Notion MCP » Create Page")

**In workflows**: MCP tools become available as nodes

**In agent nodes**: Same as regular agents

## Customizing tools

When you add an MCP tool, you can customize it:

<img src="https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/CleanShot2025-07-07at07.41.33@2x.png?fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=73042add2d9b4ec78771b1fd7fc7e899" alt="" data-og-width="798" width="798" data-og-height="1020" height="1020" data-path="images/CleanShot2025-07-07at07.41.33@2x.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/CleanShot2025-07-07at07.41.33@2x.png?w=280&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=51613a1444ee56105a0690ac02106e29 280w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/CleanShot2025-07-07at07.41.33@2x.png?w=560&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=a9c030ff90b3840bf3231eb9cc861f1e 560w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/CleanShot2025-07-07at07.41.33@2x.png?w=840&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=c82ed7dca34de0e5c313e5f87f57267c 840w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/CleanShot2025-07-07at07.41.33@2x.png?w=1100&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=be583e212d1f5bee5cb4740e9dd6c16c 1100w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/CleanShot2025-07-07at07.41.33@2x.png?w=1650&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=6285419c8411318e8bffae19770357ac 1650w, https://mintcdn.com/dify-6c0370d8/7ofzWAXbPyxqXN2g/images/CleanShot2025-07-07at07.41.33@2x.png?w=2500&fit=max&auto=format&n=7ofzWAXbPyxqXN2g&q=85&s=a4f96f8b9422ee5b5432fb3b867f0d6a 2500w" />

**Description**: Override the default description to be more specific

**Parameters**: For each tool parameter, choose:

* **Auto**: Let the AI decide the value
* **Fixed**: Set a specific value that never changes

**Example**: For a search tool, set `numResults` to 5 (fixed) but keep `query` on auto.

## Sharing apps

When you export apps that use MCP tools:

* The export includes server IDs
* To use the app elsewhere, add the same servers with identical IDs
* Document which MCP servers your app needs

## Troubleshooting

**"Unconfigured Server"**: Check the URL and re-authorize

**Missing tools**: Hit "Update Tools"

**Broken apps**: You probably changed a server ID. Add it back with the original ID.

## Tips

* Use permanent, descriptive server IDs like `github-prod` or `crm-system`
* Keep the same MCP setup across dev/staging/production
* Set fixed values for config stuff, auto for dynamic inputs
* Test MCP integrations before deploying


---

> To find navigation and other pages in this documentation, fetch the llms.txt file at: https://docs.dify.ai/llms.txt