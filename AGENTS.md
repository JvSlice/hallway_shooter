# Project guidelines

- This is a browser rail shooter built with JavaScript and Three.js.
- Develop on Raspberry Pi and play-test on iPad, phone, and desktop.
- Keep deployment compatible with GitHub Pages. Use relative paths for assets and local modules.
- Build one shared foundation that can support future sci-fi, medieval, and western games.
- Plan a shared input layer for touch, keyboard and mouse, and controllers.
- Preserve existing asset licenses and attribution when using or changing assets and vendored code.
- Make small, reviewable changes. Do not commit, push, or merge unless asked.

## Issue workflow

- `main` is the published GitHub Pages version; `develop` is the working branch.
- Read the issue and comments, inspect the relevant files, and check Git status before editing. Confirm the branch is `develop`; if it is not, report the state before making changes.
- Implement only the requested task on `develop`, preserving unrelated changes. Run checks appropriate to the change.
- Start or reuse a local preview for user testing. Before using port 8000, check whether it already serves this repository. Reuse it if it does; do not stop an unrelated process. See README.md for the Python server command and alternate port.
- Give the user the Pi's current network preview address and a short manual testing checklist. Wait for explicit confirmation that testing passed before committing, merging, or pushing.
- After release authorization, commit the issue changes on `develop`, merge into `main`, push both branches, and return to `develop`. Stop and explain any failed command or merge conflict. Never force-push.
- Close the GitHub issue only after the authorized release succeeds.
