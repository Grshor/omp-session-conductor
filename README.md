# omp-session-conductor

OMP skill: drive multiple omp project sessions from **one** conductor session.
Broadcast instructions to several projects in parallel, let each target's
agent actually do the work (full tool access in its project), read results
back from a single conversation.

```text
session cast -p myproj -p other --fresh "run tests, fix what broke, commit"
session cast --all --timeout 60 "report repo status in one line"
```

## Install

```sh
mkdir -p ~/.omp/agent/skills/session-conductor
cp SKILL.md ~/.omp/agent/skills/session-conductor/
```

Then just ask the conductor session to broadcast — the skill triggers on
"tell all projects X", "ask every project for status", etc.

## Notes

- Targets run `omp --cwd <project> -p MESSAGE` with full tool access: write
  instructions, not questions, when you want action.
- `--dry-run` first whenever targets were picked by pattern, not by hand.
- See SKILL.md for the full command surface and rules.

## License

MIT
