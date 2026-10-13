```
╭─────────────────────────────────────────────────────────────╮
│                                                             │
│   █▀▄ █▀█ █░█ █ █░░ ▄▀█ █░░ ▄▀█ █░░ ▄▀█                     │
│   █▀▄ █▄█ █▀█ █ █▄▄ █▀█ █▄▄ █▀█ █▄▄ █▀█                     │
│                                                             │
│   software engineer · go · open source · ships things       │
│                                                             │
╰─────────────────────────────────────────────────────────────╯
```

```console
$ whoami
aditya rohilla

$ cat ~/.profile
role     engineer. backend by instinct, full-stack when the job needs it.
langs    go · typescript · python · swift · sql
upstream 16 PRs merged into 9 projects · oras-go · prometheus · thanos · caddy · fiber
likes    terminals, protocols, small diffs, tests that fail first
dislikes abstractions with one implementation, 400-line PRs, "it works locally"
```

---

### `~/what-i-do`

I build the unglamorous half of software: the API that stays up, the migration
that doesn't lose a row, the money math that reconciles. Then I build the other
half too, because someone has to.

By day that means production Go services and the TypeScript front-ends that talk
to them. The rest of the time I'm fixing the libraries underneath them.

### `~/upstream`

Merged:

| project | pr | what it fixed |
|---|---|---|
| [oras-project/oras-go](https://github.com/oras-project/oras-go) | [#1556](https://github.com/oras-project/oras-go/pull/1556) | moved the `WithProperties` constructors onto `ClientBuilder` (breaking API change) |
| | [#1494](https://github.com/oras-project/oras-go/pull/1494) | added a digest algorithm option to `PackManifest` |
| | [#1486](https://github.com/oras-project/oras-go/pull/1486) | OCI store now persists its index before garbage collection |
| | [#1487](https://github.com/oras-project/oras-go/pull/1487) | extended copy now includes shared predecessors within the depth limit |
| | [#1452](https://github.com/oras-project/oras-go/pull/1452) | file store restores duplicate-named layers when `IgnoreNoName` drops the manifest |
| | [#1450](https://github.com/oras-project/oras-go/pull/1450) | `NewReferenceList` keeps the digest of a tag+digest reference |
| [prometheus/common](https://github.com/prometheus/common) | [#998](https://github.com/prometheus/common/pull/998) | OpenMetrics 2.0 parser rejects invalid UTF-8 and a trailing CR in metadata |
| | [#996](https://github.com/prometheus/common/pull/996) | a test no longer leaves the shared parser on legacy validation |
| [thanos-io/thanos](https://github.com/thanos-io/thanos) | [#9056](https://github.com/thanos-io/thanos/pull/9056) | ruler can send custom HTTP headers to query and Alertmanager endpoints |
| [caddyserver/caddy](https://github.com/caddyserver/caddy) | [#7956](https://github.com/caddyserver/caddy/pull/7956) | fastcgi explains its 411 instead of returning it bare for chunked bodies |
| [gofiber/fiber](https://github.com/gofiber/fiber) | [#4625](https://github.com/gofiber/fiber/pull/4625) | client path parameters can no longer rewrite the request they're substituted into |
| | [#4626](https://github.com/gofiber/fiber/pull/4626) | `FromParam` decodes a path parameter once, not twice |
| [vektah/gqlparser](https://github.com/vektah/gqlparser) | [#476](https://github.com/vektah/gqlparser/pull/476) | lexer combines surrogate-pair escapes in string literals |
| [andybalholm/brotli](https://github.com/andybalholm/brotli) | [#74](https://github.com/andybalholm/brotli/pull/74) | flate encoder splits matches longer than 258 bytes |
| [pierrec/lz4](https://github.com/pierrec/lz4) | [#258](https://github.com/pierrec/lz4/pull/258) | `Reader.WriteTo` writes every frame when a later one has a bigger block size |
| [jhillyerd/enmime](https://github.com/jhillyerd/enmime) | [#415](https://github.com/jhillyerd/enmime/pull/415) | reads `Content-Disposition` from MIME parts that have no `Content-Type` |

In review: ~30 more across prometheus/prometheus, alertmanager, etcd-io/bbolt,
go-tuf, kpt, echo, tview and charmbracelet/x.
[All of them →](https://github.com/search?q=author%3ARohilalala+is%3Apr+-user%3ARohilalala&type=pullrequests&s=created&o=desc)

The one I like best, fiber #4625:

```
path parameters could restructure the request they were substituted into.
a value of "../../admin" walked out of its path; one holding "@" moved the
request to another host; an empty one collapsed a segment; an overlong UTF-8
sequence read as "/" to whatever parsed the host next.
+962/-7 · merged by the lead maintainer
```

How they're found, mostly: property tests that assert the invariant rather than
the example. A fuzz target comparing whole writes against every byte-split found
a terminal bug; sweeping every rune from U+0300 to U+10FFFF proved an allowlist
I had written was quietly losing 12,351 valid cases.

### `~/projects`

| repo | what |
|---|---|
| [ClaudeUsageBar](https://github.com/Rohilalala/ClaudeUsageBar) | Claude usage limits (5-hour + weekly) live in the macOS menu bar. Swift, 100% local |
| [amazon-ml-2026-entity-resolution](https://github.com/Rohilalala/amazon-ml-2026-entity-resolution) | Amazon ML Challenge 2026 entity resolution: LightGBM stages, fine-tuned multilingual cross-encoder, dense recall. Leaderboard 0.989667 |
| [sentinel](https://github.com/Rohilalala/sentinel) | beginner's cybersecurity console: real recon tools on live data, every term explained |
| [meet-companion](https://github.com/Rohilalala/meet-companion) | Google Meet bot that joins as its own participant and plays music and video into the call |

### `~/how-i-work`

```
▸ read first        trace the whole flow before touching a line
▸ root cause        fix it once, where every caller routes through
▸ prove it          a failing test, a live browser, a real DB row. not a vibe
▸ smallest diff     the best code is the code I didn't write
▸ upstream it       found the bug in someone's library? send the patch
```

### `~/stack`

```
languages   go · typescript · python · swift · bash
backend     fiber · gorm · postgres · redis · rest
frontend    react · next · tailwind
tooling     docker · git · playwright · github actions
interests   oci & registries · observability · terminal emulators · applied ai
```

```console
$ echo "open to interesting problems"
open to interesting problems
```
