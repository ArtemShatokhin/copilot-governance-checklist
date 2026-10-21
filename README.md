# copilot-governance-checklist: an open-source control map for Copilot agents

An open-source, forkable control map for a team moving Copilot agent governance out of the Microsoft 365 admin center and into configuration it owns and reviews.

Kortix is the open-source AI Operating System: your agents, skills, company memory, and connectors in one git repo you own. This repository is the governance artifact that sentence implies. Twenty controls, each with what the Microsoft 365 admin center does for it and the file that implements the same control once the agent layer is configuration in a repository you keep. Fork it, delete the rows that do not apply, and hand the rest to a reviewer as evidence.

Kortix runs its own agents rather than Microsoft's, and the configuration surface named in the last column is a file in a git repository.

## A toggle is not a control

An admin center setting proves that someone holding the AI Administrator role pressed Save. It does not say what the setting was on the day of the incident, or who moved it, or why. A settings page has no diff, so the review of a settings page is a review of a screenshot.

The controls that survive an audit are the ones written in a file. The file has a diff, the diff has an author, the author asked a second person to approve it, and the approval is stored next to the change. That chain is what an auditor asks for, and no toggle produces it.

Microsoft documents each of its toggles accurately, and every Microsoft cell carries the page it came from. What Microsoft does not publish is the mapping from those toggles to a control you can hand over, because for Microsoft the tenant is the control. This repository is that mapping for a team that keeps its agent layer in a repository, with one rule: every row names the surface that implements the control, so a reader can open the file and check.

## What the file looks like

The Kortix project manifest splits an agent in two, and both halves live in the repo. Governance keys sit in `kortix.yaml`. Behaviour sits in the agent's markdown file.

```yaml
agents:
  kortix:
    file: agents/kortix.md
    connectors: all
    secrets: all
    kortix_permissions: all
    skills: all
    workspace: { project_repository: true }
```

The manifest header says where each half lives, in its own words:

```yaml
# `agents:` map per project — GOVERNANCE ONLY (connectors/secrets/
# kortix_permissions/skills/workspace/enabled), plus `file`, the path of the
# agent's `.md`. Agent BEHAVIOR (description, model, mode, temperature,
# permission, the prompt itself, …) lives entirely in that `.md`'s
# frontmatter + body — a stock OpenCode agent file works as-is.
```

Deny-by-default is what makes a forkable map worth reading. The same header says it directly:

```yaml
# v2 is deny-by-default: an omitted connectors/secrets/kortix_permissions/
# skills grant resolves to "none", so a scoped specialist starts locked down.
```

An omission is a line a reviewer can see and ask about. A settings page opens with the toggles already in some position, and nobody can tell which positions a person chose.

The agent file states the rule the whole map rests on:

> Only what you commit + push survives.

A session runs on its own branch. Nothing it produces reaches the default branch until the change request merges, and an agent cannot merge one it opened unless an administrator granted it the merge capability. The file under review and the configuration that runs are then the same object at the same commit.

## What the file holds

Four facts the map rests on:

- Session work reaches `main` through a change request. Merge is default-deny for agents.
- Approval gates you set. Off until you set them.
- Every action is recorded. Reading, exporting and streaming the audit log depend on the plan.
- Secrets are encrypted at rest with a key per project.

The second one is the reason this checklist exists. A gate that is off until someone writes `require_approval` into the file is a control someone can point at. A gate that "should be on" in a tenant nobody re-checked is a hope.

## How to use the map

`controls.csv` has one row per control and five columns.

| Column | What goes in it |
| --- | --- |
| `control` | The name of the control, in the words a reviewer uses. |
| `what_microsoft_admin_center_does` | The admin center behaviour, briefly, as Microsoft documents it. |
| `microsoft_source` | The `learn.microsoft.com` page that behaviour came from. Open it before you cite a cell. |
| `kortix_configuration_surface` | The file or product surface that implements the control. |
| `notes` | What a reviewer should ask about that row, and which source row the claim rests on. |

The usual loop: fork the repository, edit `notes` to your own environment, delete rows that do not apply to you, add the rows your auditors ask for, and open a pull request per change. The pull request is the artifact. A control that lives in a reviewable diff has a history, and the history is the evidence.

## Where the map does not reach

Three rows read `not supported today` in the Kortix column: seat assignment per agent, self-service purchase, and the preview programme. Kortix has no per-agent entitlement to assign, no member-facing purchase path, and no preview toggle a group can be granted. Rather than invent a surface, each row says so and the notes explain why there is nothing to configure, so the gap sits in the diff next to the controls that are covered. A map that hides its holes is worth less than one that lists them.

## Read the Microsoft column with a date on it

Microsoft ships admin center changes constantly and reorganises the navigation with them. Every page used here is listed in `SOURCES.md` with the date it was read. Check the page again before you put a cell in front of an auditor, and treat a cell you have not re-read as a claim you cannot make yet.

## Links

- [Kortix](https://kortix.com), the project this map is written from
- [Open-source Copilot agent management](https://opensourcecopilotalternative.com/copilot-agent-management), the longer argument for keeping agent policy in git
- [SOURCES.md](SOURCES.md), every page used to build the table, with the date read

## Contributing

Fork, change one row, open a pull request with the reason in the message. Keep the column headers as they are, keep quoted fields quoted, and put a source URL in `microsoft_source` for any cell you touch. If a row says `not supported today` and you know how to implement it, say how in the pull request.
