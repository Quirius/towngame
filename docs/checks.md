# Targeted checks

Run from the repository root. There is no build, dependency install or application
suite; this is a design-documentation project. Choose the affected row; these are
starting points, not a mandatory checklist.

A check that does not run, or that matches nothing, is not a pass. Do not repeat
passing checks without a relevant change.

| Area / source | First check |
| --- | --- |
| Any documentation edit | Confirm changed links resolve, then `git diff --check` |
| `TOWNGAME_DESIGN.md` | Confirm links, and confirm the section names cited in `DESIGN_INDEX.md` still resolve |
| `DESIGN_INDEX.md` | Re-verify every cited line number against a real heading, and refresh stale line numbers |
| Supersede log | Confirm each logged supersession matches the marked revision in the design document |
| `docs/AGENTS.md`, task routes | Confirm each route and line reference points at the intended section |
| Documentation only (default) | The three checks above; there is no application suite |

```sh
# every relative markdown link resolves
for f in $(find . -name '*.md'); do
  grep -oE '\]\(([^)#]+\.md)' "$f" | sed 's/](//' | sort -u | while read -r l; do
    [ -f "$(dirname "$f")/$l" ] || echo "BROKEN in $f -> $l"
  done
done

# no whitespace errors
git diff --check

# every line number cited in the index is a real heading
grep -E '^\| [0-9]+ \| [0-9]+ \|' docs/DESIGN_INDEX.md \
  | awk -F'|' '{gsub(/[^0-9]/,"",$3); print $3}' | sort -n -u | sed 's/^0*\([0-9]\)/\1/' > /tmp/idx.txt
grep -nE '^#{1,4} ' docs/TOWNGAME_DESIGN.md | sed 's/:.*//' | sort -n -u > /tmp/heads.txt
for n in $(cat /tmp/idx.txt); do grep -qx "$n" /tmp/heads.txt || echo "NOT A HEADING: $n"; done
```

The index check matters because line numbers go stale whenever the design document is
edited above them. Section names are the stable identifiers.
