# Project HQ reporting contract

Project HQ reads these TownGame reporting files from the published reporting branch. `STATUS.yaml` summarizes the latest inspected pushed product and documentation revision. The single YAML front matter blocks in `ROADMAP.md` and `DECISIONS.md` are the machine-readable plan and decision lists; the prose below them adds context.

Version-one fields are `STATUS.yaml`: `schema_version`, `project_id`, `name`, `repository`, `status`, `description`, `objective`, `phase`, `progress`, `next_action`, `updated_at`, `source`, `summary`, and `evidence`; `ROADMAP.md`: `schema_version`, `project_id`, `plans`, and `milestones`; `DECISIONS.md`: `schema_version`, `project_id`, and `decisions`. Status is `Active`, `Planning`, `In Progress`, `Review`, `Archived`, or null. Plan and milestone states are `planned`, `blocked`, or `completed`; decision states are `open` or `resolved`. Plan windows are `Today`, `This week`, `Next week`, `Later`, or `Backlog`, and priorities are `high`, `medium`, or `low`. Progress has a nullable percent and `manual` or `unknown` basis. Evidence uses repository-relative `path`, full pushed `ref`, and `note` (or an exact external `url` and `note`). All known timestamps are UTC ISO 8601 ending in `Z`.

Use schema version 1 and stable `towngame` IDs. Publish the reporting files on `main`, the repository's established development and reporting branch. The `source.branch` and full `source.commit` in `STATUS.yaml` identify the pushed revision inspected for claims; they are not the reporting commit. The importer must independently record the commit from which it reads these files and explicitly select this branch.

The authoritative design is [TOWNGAME_DESIGN.md](../docs/TOWNGAME_DESIGN.md), located through [DESIGN_INDEX.md](../docs/DESIGN_INDEX.md). These reports summarize that design without replacing it. Accepted or mostly settled design does not mean implemented, tested, or released. Unknown project completion remains `null` with basis `unknown`. Unknown decision dates, completion times, and deadlines also remain null. In the absence of a documented owner priority or schedule, plans use `medium` and `Backlog` as reporting defaults, not commitments. Add `window_as_of` whenever evidence supports a relative window such as `This week`.

For substantive work, read these files and the relevant source documents. Keep manual plans and stable IDs, update a plan or decision when its source changes materially, and add evidence objects tied to full pushed commit SHAs. After product or design changes have been pushed, refresh the reporting snapshot against the pushed branch and publish a separate reporting commit under repository Git policy. Do not mark local or unpushed work complete in published data; explain it in the session handoff. A reporting-only commit is not a new product revision and needs no timestamp-only follow-up. Report push failures, stale snapshots, and unresolved branch ambiguity explicitly. A pushed report does not prove Project HQ synchronization.

## Reporting completion gate

After substantive code/design work, finish the Project HQ reporting update before
the final push/handoff. Review changes since STATUS.yaml source.commit and refresh
affected status, plans, blockers, milestones, decisions and evidence. Set the
source SHA only to the actual reviewed product/design commit, not the reporting
commit; never advance it merely to suppress a warning or infer progress from
activity. Preserve owner plans, stable IDs and unknown values.

Run `python scripts/check_project_hq_freshness.py --strict` after the report
update and before pushing its reporting commit. Resolve any stale-report result;
if blocked, disclose the remaining stale scope rather than claiming completion.
Follow existing Git rules, push the reporting commit, and confirm its remote
publication before saying the report is published. Do not create timestamp-only
follow-up commits or claim dashboard synchronization without checking it.

The default GitHub Actions invocation is advisory for stale reports: it emits a
warning and succeeds. Missing/invalid source metadata and checker/Git errors
still fail. A successful Action does not certify report freshness; HQ retains its
independent amber stale-report warning. The `--strict` mode is the agent's
completion gate and fails on stale reports as well.

