# Hallway Shooter

A browser rail shooter built with JavaScript and Three.js. `index.html` is the current 3D game; `straight-corridor.html` is an earlier corridor demo. The game loads local modules and the robot asset through relative paths, so serve the repository root over HTTP instead of opening the HTML file directly.

## Local preview on the Raspberry Pi

From the repository root, first check whether port 8000 is already in use:

```sh
ss -ltnp '( sport = :8000 )'
```

If a server is listening, open `http://127.0.0.1:8000/` on the Pi and confirm it serves this repository before reusing it. Leave an unrelated server running and choose another free port, such as 8001. If port 8000 is free, start the preview with Python:

```sh
python3 -m http.server 8000 --bind 0.0.0.0
```

Keep that terminal open while testing. No build step or added dependencies are needed. Find the Pi's current local network address with `hostname -I`, then open `http://<pi-address>:8000/` on an iPad or phone connected to the same network. Replace `8000` in both the command and URL if using another port. `localhost` on the iPad refers to the iPad, not the Pi.

## Branch and release workflow

`main` is the published GitHub Pages version. `develop` is the working version for issues.

1. Read the issue and comments, inspect the existing files, check Git status, and confirm the branch is `develop` before making changes. Report the current state first if another branch is checked out.
2. Implement only the requested change on `develop`, preserving unrelated changes, and run checks appropriate to it.
3. Start or reuse a local preview. Check port 8000 before using it; leave any unrelated process alone. Share the Pi's current preview address and a short manual testing checklist.
4. Wait for explicit confirmation that testing passed before committing, merging, or pushing.
5. After release authorization, commit the issue changes on `develop`, merge into `main`, push both branches, and return to `develop`. Stop and explain any failed command or merge conflict. Never force-push.
6. Close the GitHub issue only after the authorized release succeeds.
