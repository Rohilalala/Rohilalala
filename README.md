```
╭─────────────────────────────────────────────────────────────╮
│                                                             │
│   █▀▄ █▀█ █░█ █ █░░ ▄▀█ █░░ ▄▀█ █░░ ▄▀█                     │
│   █▀▄ █▄█ █▀█ █ █▄▄ █▀█ █▄▄ █▀█ █▄▄ █▀█                     │
│                                                             │
│   software engineer · backend-leaning · ships things        │
│                                                             │
╰─────────────────────────────────────────────────────────────╯
```

```console
$ whoami
aditya rohilla

$ cat ~/.profile
role     engineer. backend by instinct, full-stack when the job needs it.
langs    go · typescript · python · swift · sql
likes    terminals, protocols, small diffs, tests that fail first
dislikes abstractions with one implementation, 400-line PRs, "it works locally"
```

---

### `~/what-i-do`

I build the unglamorous half of software: the API that stays up, the migration
that doesn't lose a row, the money math that reconciles. Then I build the other
half too, because someone has to.

Lately that means production Go services, TypeScript front-ends that talk to
them, and enough infrastructure to keep both honest.

### `~/how-i-work`

```
▸ read first        trace the whole flow before touching a line
▸ root cause        fix it once, where every caller routes through
▸ prove it          a failing test, a live browser, a real DB row. not a vibe
▸ smallest diff     the best code is the code I didn't write
▸ upstream it       found the bug in someone's library? send the patch
```

### `~/open-source`

Merged into [gofiber/fiber](https://github.com/gofiber/fiber), an Express-style
Go web framework with 40k stars. Both in its HTTP client:

```
#4625  path parameters could restructure the request they were substituted into.
       a value of "../../admin" walked out of its path; one holding "@" moved the
       request to another host; an empty one collapsed a segment; an overlong
       UTF-8 sequence read as "/" to whatever parsed the host next.
       +962/-7 · merged by the lead maintainer

#4626  FromParam decoded a path parameter twice, so a literal %2F arrived as "/"
```

Open, in review:

```
caddyserver/caddy #7956   fastcgi returned a bare 411 for a chunked body (approved)
labstack/echo     #3072   BodyLimit handed back 50 bytes against a 5 byte limit
rivo/tview        #1165   Escape() left non-ASCII tags unprotected, dropping a char
charmbracelet/x   ×7      grapheme clusters split across writes, a parser panic
                          reachable from untrusted output, CJK dropped at line ends
```

How they were found, mostly: property tests that assert the invariant rather than
the example. A fuzz target comparing whole writes against every byte-split found
the terminal bug; sweeping every rune from U+0300 to U+10FFFF proved an allowlist
I had written was quietly losing 12,351 valid cases.

### `~/stack`

```
languages   go · typescript · python · swift · bash
backend     fiber · gorm · postgres · redis · rest
frontend    react · next · tailwind
tooling     docker · git · playwright · github actions
interests   terminal emulators · developer tooling · applied ai
```

### `~/elsewhere`

```
github   @Rohilalala
```

```console
$ echo "open to interesting problems"
open to interesting problems
```
