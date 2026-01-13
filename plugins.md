# Plugins

> Extend Dify with custom models, tools, and integrations through modular components

Plugins are how Dify connects to everything—model providers, external APIs, custom tools. They're modular components that extend your workspace capabilities that you install once but can use everywhere.

<img src="https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugins-tab.png?fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=2572299ff6c6bbf31f4a9718de7f107e" alt="" data-og-width="1051" width="1051" data-og-height="478" height="478" data-path="images/plugins-tab.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugins-tab.png?w=280&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=7575ebebe00e2acea882bdb933c04ef9 280w, https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugins-tab.png?w=560&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=f597f66b329efbc1d8f321424817e58d 560w, https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugins-tab.png?w=840&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=a9e98d09bd10c841a662db9fa720ad43 840w, https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugins-tab.png?w=1100&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=86638848cf62446ce8c4417ceb88d873 1100w, https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugins-tab.png?w=1650&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=2525fa0f7db1b91d79e477d3fbb1dc2a 1650w, https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugins-tab.png?w=2500&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=e4976c0139b9e0586d1ff3b43f98f975 2500w" />

Access plugin management through the Plugins tab in your workspace.

## How Plugins Work

<img src="https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugin-management.png?fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=3869e637fe3ddaab2268d9f944ce8468" alt="" data-og-width="3024" width="3024" data-og-height="1902" height="1902" data-path="images/plugin-management.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugin-management.png?w=280&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=5fe6d31375d0e1a3b94693dc72898108 280w, https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugin-management.png?w=560&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=f856b9a61716c8bbec1994fb8fb89143 560w, https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugin-management.png?w=840&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=e77fc663206e0d2a6ab127a393359ef1 840w, https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugin-management.png?w=1100&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=26b8322b6a2d84e281129b51d920ce4b 1100w, https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugin-management.png?w=1650&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=13afb1fc174db8cdd8b4c8cafe18a7d6 1650w, https://mintcdn.com/dify-6c0370d8/MiGqQWUuc2Ca3g05/images/plugin-management.png?w=2500&fit=max&auto=format&n=MiGqQWUuc2Ca3g05&q=85&s=781fb92da7536bc2f9ea79257795dca4 2500w" />

Plugins are workspace-scoped. When you install a plugin, every application in your workspace can use it. Team members access plugins based on their roles:

<Tabs>
  <Tab title="Owners & Admins">
    Install, configure, and remove plugins for the entire workspace
  </Tab>

  <Tab title="Editors & Members">
    Use installed plugins in applications they create or edit
  </Tab>
</Tabs>

## Installing Plugins

<CardGroup cols={3}>
  <Card title="Marketplace" icon="store">
    Official and partner plugins, tested and maintained
  </Card>

  <Card title="GitHub" icon="github">
    Install from any public repository with URL + version
  </Card>

  <Card title="Local Upload" icon="upload">
    Custom .zip packages for private or internal plugins
  </Card>
</CardGroup>

## What Plugins Really Are

Think of plugins as the bridge between Dify and the outside world:

<CardGroup cols={2}>
  <Card title="Model Providers" icon="microchip">
    Every LLM in Dify (OpenAI, Anthropic, etc.) is actually a plugin
  </Card>

  <Card title="Tools & Functions" icon="wrench">
    API calls, data processing, calculations—all plugin-based
  </Card>

  <Card title="Custom Endpoints" icon="plug">
    Expose your Dify apps as APIs that external systems can call
  </Card>

  <Card title="Reverse Invocation" icon="arrows-rotate">
    Plugins can call back into Dify to use models, tools, or workflows
  </Card>
</CardGroup>

## Workspace Plugin Settings

Control plugin permissions in your workspace settings:

<AccordionGroup>
  <Accordion title="Installation Rights">
    **Everyone** - Any member can install plugins
    **Admin Only** - Only workspace admins can install (recommended)
  </Accordion>

  <Accordion title="Debug Access">
    **Everyone** - All members can debug plugin issues
    **Admin Only** - Restrict debugging to admins
  </Accordion>

  <Accordion title="Auto-updates">
    Choose update strategy (security only vs. all updates) and specify which plugins to include or exclude
  </Accordion>
</AccordionGroup>

After installing, most plugins need configuration—API keys, endpoints, or service settings. These apply workspace-wide.

## Plugin Installation Restrictions

<Callout icon="lock" color="#0033FF">Enterprise Only</Callout>

In enterprise workspaces, you might see installation restrictions when browsing the plugin marketplace:

**What you'll encounter:**

* The "Install Plugin" dropdown in Plugins → Explore Marketplace may show limited options
* Installation confirmation dialogs will indicate if a plugin is blocked by policy
* When importing apps with plugins (DSL files), you'll see notices about restricted plugins

**Plugin badges in marketplace:**

![](https://assets-docs.dify.ai/2025/06/c2bfdfbb2132848e589073600e55ffab.png)

Look for these badges to identify plugin types—your workspace may only allow certain types based on admin settings.

<Info>
  If you can't install a needed plugin, contact your workspace admin. They control which plugin sources (marketplace, GitHub, local files) and types (official, partner, third-party) are allowed.
</Info>

## Building Custom Plugins

Develop plugins using Dify's SDK when you need custom functionality:

1. Get a debugging key from Settings → Plugins → Debugging
2. Build and test your plugin locally
3. Package as a .zip with manifest and dependencies
4. Distribute privately or publish to the marketplace


---

> To find navigation and other pages in this documentation, fetch the llms.txt file at: https://docs.dify.ai/llms.txt