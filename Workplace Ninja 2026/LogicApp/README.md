<!-- jr-brand:start -->
<p align="center">
  <a href="https://jannikreinhard.com/">
    <img src="https://raw.githubusercontent.com/JayRHa/.github/main/assets/readme/brand-header.png" alt="Jannik Reinhard — I help enterprises ship secure AI agents" width="100%">
  </a>
</p>
<p align="center">
  <a href="https://jannikreinhard.com/">Website</a> ·
  <a href="https://www.linkedin.com/in/jannik-r/">LinkedIn</a> ·
  <a href="https://x.com/jannik_reinhard">X</a> ·
  <a href="https://www.youtube.com/@jannikreinhard">YouTube</a>
</p>
<!-- jr-brand:end -->

# Logic App designer demo

This ARM template recreates the visual automation example from **Workplace Ninja 2026 / Intune AI Intelligence**.

**Daily at 08:00 Berlin → Graph GET → filter noncompliant/error devices → condition → summary.**

The Logic App is deliberately deployed **disabled**. It is a designer draft, not the working daily monitor. The `Review_in_Teams` action is a **Compose placeholder**, not a Teams connector. The Graph request is configured for Managed Identity, but the template does not grant Graph permissions. It reads only the first page and does not implement full health coverage or production error handling.

For the tested health-check implementation, use [the Azure Automation runbook](../Automation/).

## Open in the Azure designer

1. Create or select a demo resource group.
2. In Azure Portal, open **Deploy a custom template → Build your own template in the editor**.
3. Paste `logic-intune-health-demo.arm.json`, review the location and workflow name, and deploy.
4. Open the resulting Logic App's **Designer**. Keep it disabled for the visual demo.

| ARM parameter | Default |
| --- | --- |
| `location` | The resource group's location |
| `workflowName` | `logic-intune-health-demo` |

The template contains no tenant-specific IDs, credentials or Teams webhook URL. It creates a System Assigned Managed Identity for the workflow, without assigning permissions.

<!-- jr-brand-footer:start -->
---

[Articles and guides](https://jannikreinhard.com/) · [Repository index](https://github.com/JayRHa/.github/blob/main/REPOSITORIES.md)
<!-- jr-brand-footer:end -->
