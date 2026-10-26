# CLAUDE.md: data-url

One public file, `url`: up to three plain https addresses in order, comma separated, on one line. Every app reads it about once an hour (SYSKit `SYSHosting`), keeps the ones that answer `app.json` with the studio's data, and tries them in that order. A change here reaches every installed app within the hour, so treat each push as a release.

## Never do
- Never push a test value. Test with a simulator and the debug launch arguments in `pes/SPM/SYSKit/README.md` instead. Earlier test pushes polluted this history.
- Never write anything but https addresses (no spaces, no query, no trailing slash), at most three, first the host that works best. The GitHub copy of the handbook is the built-in address: `https://raw.githubusercontent.com/erbittuu-studio/handbook/main/content`.
- Never push unless the owner says so in that message. Never add other files or code here.

## How to change it
Edit `url`, run `node ../faststore/tools/studio-check.mjs` (it checks the format), commit with `data: <what changed>`. Commit straight to `main`: this repo is one line, so it has no release branches. Add a second host only when the data is already served there and `app.json` answers.
