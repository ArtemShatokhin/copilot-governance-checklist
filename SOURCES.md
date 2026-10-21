# Sources

Every page the control map was built from, and the date each was read. Read date is 2026-10-21 for all of them.

## Microsoft 365 admin center and agent management

| Page | URL | Read | Used for |
| --- | --- | --- | --- |
| Manage Microsoft Copilot settings in the Microsoft 365 admin center | https://learn.microsoft.com/en-us/microsoft-365/copilot/microsoft-365-copilot-page | 2026-10-21 | Frontier access, self-service purchase, AI providers for other models |
| Governance and lifecycle actions for agents | https://learn.microsoft.com/en-us/microsoft-365/admin/manage/agent-actions | 2026-10-21 | Activation and publishing, install and uninstall, block and unblock, delete and restore |
| Agent settings in the Microsoft 365 admin center | https://learn.microsoft.com/en-us/microsoft-365/admin/manage/agent-settings | 2026-10-21 | Agent and plugin access, sharing, user access, agent management rules |
| Agent registry in the Microsoft 365 admin center | https://learn.microsoft.com/en-us/microsoft-365/admin/manage/agent-registry | 2026-10-21 | Export to Excel, including the instructions field |
| Assign or unassign licenses for users in the Microsoft 365 admin center | https://learn.microsoft.com/en-us/microsoft-365/admin/manage/assign-licenses-to-users | 2026-10-21 | Per-user seat assignment |
| Remove a former employee and secure data | https://learn.microsoft.com/en-us/microsoft-365/admin/add-users/remove-former-employee | 2026-10-21 | Offboarding a person |

## Copilot behaviour, data and audit

| Page | URL | Read | Used for |
| --- | --- | --- | --- |
| Copilot Cowork overview | https://learn.microsoft.com/en-us/microsoft-365/copilot/cowork | 2026-10-21 | Approval of each action before it happens |
| How data is protected and audited in Microsoft 365 and Microsoft Copilot | https://learn.microsoft.com/en-us/microsoft-365/copilot/microsoft-365-copilot-architecture-data-protection-auditing | 2026-10-21 | Service boundary, labels and permissions on outputs, where interaction data is stored |
| Audit logs for Copilot and AI applications | https://learn.microsoft.com/en-us/purview/audit-copilot | 2026-10-21 | CopilotInteraction records, 180-day default, audit retention policies, admin operations |
| Use Microsoft Purview to manage data security and compliance for Microsoft 365 Copilot | https://learn.microsoft.com/en-us/purview/ai-m365-copilot | 2026-10-21 | Sensitivity labels, DSPM, eDiscovery and audit as incident evidence |
| Configure and manage connections (Copilot Studio) | https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-connections | 2026-10-21 | Where an agent's credentials live, connection status |
| Work with Power Platform environments in Copilot Studio | https://learn.microsoft.com/en-us/microsoft-copilot-studio/environments-first-run-experience | 2026-10-21 | Environment types and region for where an agent runs |
| Multistage and AI approvals in agent flows (preview) | https://learn.microsoft.com/en-us/microsoft-copilot-studio/flows-advanced-approvals | 2026-10-21 | Read for context on approval stages in agent flows; no cell depends on it |

## Kortix

| Page | URL | Read | Used for |
| --- | --- | --- | --- |
| Starter project manifest | https://github.com/kortix-ai/suna/blob/dev/packages/starter/templates/base/kortix.yaml | 2026-10-21 | The governance block quoted in the README, the deny-by-default comment, the agents map, sandbox templates, env block |
| Starter agent file | https://github.com/kortix-ai/suna/blob/dev/packages/starter/templates/base/agents/kortix.md | 2026-10-21 | The session rule quoted in the README |
| Kortix brand claims | `seo/skills/kortix-brand/references/verbal/claims.md` (Kortix brand kit, not a public URL) | 2026-10-01 verification date recorded in the file | The rows each Kortix cell traces to: permissions, approval gates, audit, secrets, models, hosting, path to main, SSO, connector policy, manifest facts |
| Kortix product page | https://kortix.com | 2026-10-21 | Linked from the README as the plain brand link |

## Campaign pages linked from the README

| Page | URL | Read | Note |
| --- | --- | --- | --- |
| Open-source Copilot agent management | https://opensourcecopilotalternative.com/copilot-agent-management | 2026-10-21 | Live and linked |
| Copilot admin center page | https://opensourcecopilotalternative.com/copilot-admin-center | 2026-10-21 | Returned 404 on this date, so it is not linked from the README until it is published |

## What is not in here

Explanations of the Microsoft toggles in prose, from vendor blogs and consultancies, are not used. Every Microsoft cell comes from the `learn.microsoft.com` page named in its `microsoft_source` field. Nothing in the table describes a Kortix surface that is not in the manifest or the brand claims file.
