# Contributing to MiraCLO

Every change to MiraCLO must be easy to understand months later, even without the person who made it. These rules apply to all repositories in the MiraCLO-OS organization.

## Commit messages

```
<area>: <what changed, imperative, max ~72 characters>

<why the change was needed — the bug, request or goal>
<what was changed and anything non-obvious, e.g. values before/after>
<how it was tested, if relevant>

Change-Type: feature | fix | branding | build | upstream
```

**Area** is the part of the project, matching the folder or component:

| Area | Use for |
| --- | --- |
| `SystemUI` / `qs` | Status bar, Quick Settings, lock screen |
| `Settings` | The Settings app |
| `marble` | Device-specific changes |
| `manifest` | Which repositories are synced |
| `MiraCLO` | Branding, version, build scripts |
| `dolby`, `kernel`, … | Any other component, by its own name |

### Example

```
SystemUI: Make QS tiles square so icon tiles are perfect circles

Icon-only Quick Settings tiles were wider than tall on marble, which
made them ovals. The tile shape already uses a radius of height / 2,
so matching height to column width turns them into circles.

common_tile_default_tile_height: 72dp -> 86dp
Tested on marble at the default display size.

Change-Type: feature
```

## Rules

1. **One logical change per commit.** Do not mix a fix with a feature.
2. **Never commit secrets.** Release keys, tokens and passwords never go into any repository.
3. **Record every change in the manifest's `CHANGELOG.md`** in the same session.
4. **Upstream fixes** (a bug in someone else's tree) say so in the body and credit the original author.
5. **Tag releases** in `manifest` and `android_vendor_aospa` as `v<version>` (e.g. `v1.0`).
