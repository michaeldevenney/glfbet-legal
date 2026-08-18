# glfbet-legal

Public legal pages for the **glfbet** mobile app, served via GitHub Pages.

This repo is public because the pages must be publicly reachable — app stores
require live URLs:

- Apple App Store and Google Play both require a privacy policy URL, and both
  expect an account-deletion path to be documented.

(The pages were originally stood up for Meta's Facebook Login review. Facebook
sign-in was dropped on 2026-08-17, but the pages are still required by the app
stores, so they stay.)

The app source itself lives in the private `glfbet` repo. Nothing here should
reference internal infrastructure, tenant IDs, or anything not intended to be
world-readable.

## Pages

| Path | Purpose |
| --- | --- |
| `/` | Index linking to the three documents |
| `/privacy/` | Privacy Policy |
| `/terms/` | Terms of Service |
| `/delete-my-data/` | Account and data deletion instructions |

## Keeping these accurate

The privacy and deletion pages describe **actual app behaviour**, not
boilerplate. If any of the following change in the `glfbet` repo, update these
pages in the same change:

- The set of stored fields on `Profile`, `ContactHash`, `Device`, `Friendship`,
  or `Invite`.
- How contact matching hashes data, or when hashes are purged.
- The in-app path to export and delete (currently **Settings → Export my
  data** / **Delete account**).
- Any new third-party SDK, analytics, or data processor.

## Local preview

```bash
python -m http.server 8000
```

Then open <http://localhost:8000>. Note that the pages use absolute
`/glfbet-legal/...` paths to match the GitHub Pages project-site prefix, so
local links resolve only if you serve from a parent directory named
`glfbet-legal`.
