# Package authoring format (schema 1)

Each custom package is a folder under `packages/<package-id>/` containing a `package.json`
(schema 1) plus its content files. Verified against the live Motion package format.

## package.json shape

```json
{
  "schemaVersion": 1,
  "id": "<package-id>",
  "name": "<Human Name>",
  "version": "1",
  "description": "<what it does; note it self-onboards and only stages files on install>",
  "categories": ["brand-starter-26"],
  "installPolicy": "auto",
  "updatePolicy": "auto",
  "uninstallPolicy": "allowed",
  "resources": [
    {
      "id": "readme",
      "type": "file",
      "executable": false,
      "sourcePath": "README.md",
      "target": { "root": "agent_brain", "path": "<package-id>/README.md" }
    },
    {
      "id": "skill",
      "type": "file",
      "executable": false,
      "sourcePath": "skills/<name>/SKILL.md",
      "target": { "root": "agent_skills", "path": "<package-id>/<name>/SKILL.md" }
    },
    {
      "id": "activation",
      "type": "package_instruction",
      "executable": false,
      "sourcePath": "instructions/activation.md",
      "target": { "root": "package_instructions", "path": "<package-id>/activation.md" }
    }
  ]
}
```

## Target roots

- `agent_brain` -> `/agent/brain/...` (durable docs, SOPs, data templates)
- `agent_skills` -> `/agent/.agents/skills/...` (invocable skills)
- `package_instructions` -> `/agent/.runneth/packages/instructions/...` (always-loaded activation guidance)

## Rules for these packages

- **Workspace-agnostic.** No Harry's/Flamingo workspace IDs, ad account IDs, product codes,
  naming conventions, Slack channel IDs, Drive folder IDs, or secrets baked in.
- **Self-onboarding.** Put a `package_instruction` activation file that: offers setup at most
  once per conversation, resolves the workspace only from Motion context, discloses side
  effects (connected-account reads, routine creation, brain writes), and waits for an explicit
  human yes before doing anything.
- **Install stages files only.** Setup actions (routines, apps, secrets, connected reads) never
  run automatically on install.
- **App-backed packages** ship the app source under `agent_brain` and let activation build the
  app in the target instance after approval, rather than assuming a prebuilt app.
