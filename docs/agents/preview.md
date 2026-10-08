# Preview

Where `verify-epic` finds the running app for a pull request. Keep exactly one **Source**.

**Source:** github-deployments

- `github-deployments`: the host reports each preview to GitHub as a deployment (Vercel does). The newest successful one for the PR's head commit is used.
- `url-pattern`: previews live at a predictable address (Coolify, self-hosted). Set **Pattern** below; `{number}` is the PR number.
- `local`: there are no previews; `verify-epic` starts the app from the PR's head, the way the project runs locally.

**Protection:** none

When previews are protected, name the environment variables holding the credentials here (for example Vercel's `VERCEL_AUTOMATION_BYPASS_SECRET`), and put their values in `.sandcastle/.env`. Never write the values in this file.

## Mobile app

The mobile app (`area:mobile`) has no browser preview, and the sandbox can't run an iOS or Android build. For a mobile epic, verify-epic checks what it can reach (the API contracts, and any web build of the app) and opens a `ready-for-human` ticket listing the acceptance criteria to check on a simulator or device.
