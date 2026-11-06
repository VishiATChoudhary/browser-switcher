# browser-switcher (chromep)

Agents (Claude Code, Codex) open links in whichever Chrome profile was used last. `chromep` fixes that by naming each profile and opening URLs in a chosen one.

Identity is the profile's signed-in **email**, read live from Chrome's `Local State`. Chrome's folder names (`Profile 11`) and display names are only cached, so names survive Chrome renaming or renumbering profiles.

```sh
chromep calibrate              # window: name each profile, pick default, "Identify" opens a banner in that profile
chromep list
chromep open work https://...  # by name, email, email prefix, or folder
chromep open https://...       # default profile
chromep default work
chromep alias you@company.com work
```

- Config: `~/.config/chromep/profiles.json` (keyed by email)
- `chromep-browser`: `BROWSER=` hook for tools that honour it (gh, python webbrowser, ...)
- Install: symlink both scripts into `~/.local/bin`. Stdlib Python 3 only.
