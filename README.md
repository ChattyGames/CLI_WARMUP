# CLI Warm-Up

A five-minute daily command-line warm-up for AP Networking. Each screen shows a terminal session and a short mission. The student types the next command. A correct answer prints realistic output and unlocks the next screen.

- Two tracks: **Linux** and **Windows PowerShell**.
- One set for every class meeting from Wed 10/28 to Tue 12/15 (see [SCHEDULE.md](SCHEDULE.md)).
- The page opens **today's set automatically**. Students use one link all semester.
- Nothing is recorded. No scores, names or typed text leave the student's browser.
- Nothing really runs. The terminal is a simulation, so students cannot break anything.

## Student link

After you turn on GitHub Pages (below), the link is:

```
https://YOUR-USERNAME.github.io/YOUR-REPO/
```

Add a day to the end to open a specific set:

| Link ending | Opens |
|---|---|
| (nothing) | today's set, or the most recent one on weekends and breaks |
| `#d05` | Day 5 |
| `#2026-11-06` | the set for that date |

The dropdown in the page header switches days too. Choose **Today** to go back to automatic.

## Put it on GitHub Pages

1. On GitHub, choose **New repository**. Name it (for example `cli-warmup`) and make it **Public**. Free GitHub Pages needs a public repository.
2. Choose **Add file, then Upload files**. Drag in `index.html`, `README.md` and `SCHEDULE.md` (unzip first), then **Commit changes**.
3. Open **Settings, then Pages**. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to **main**, folder **/ (root)**, and Save.
4. Wait about a minute. The link appears at the top of the Pages screen.
5. **Open the link on a student Chromebook before class.** If the school filter blocks it, try the same file on another host.

To change anything later, edit `index.html` on GitHub (pencil icon) and commit. The site updates in about a minute.

## How the page is built

Everything is in one file, `index.html`, with no libraries.

- `DAYS` holds every day: an id (`d01`), a `date`, a `label`, a `wo` (work order line) and a `tracks` object with `linux` and `ps` screens.
- `LX` and `PX` are libraries of reusable command blocks. A block holds the mission text, the accepted answers, the printed output, a hint, and a short "why".
- `addDay(...)` builds a day by listing block names. Commands come back in later days as retrieval practice.

### Add a day

In `index.html`, find the last `addDay(...)` call (Day 18) and add yours right after it:

```js
addDay('d19', '2026-12-16', 'Day 19 · Wed 12/16', 'Work order: Example', 'cp-ubuntu',
  ['whoami', 'id', ['ip_route', { task: 'Retrieval: which address is the default gateway?' }]],   // Linux blocks
  ['whoami', 'ipconfig']);                                                                         // PowerShell blocks
```

An item is a block name, or `[blockName, { overrides }]` to change the mission text or anything else for that day.

### Add a command

Add a block to `LX` or `PX`:

```js
whoami: {
  task: 'Who are you logged in as?',        // mission shown above the terminal
  accept: [{ re: /^whoami$/ }],             // every accepted way to type it
  answer: 'whoami',                         // shown by the "Show me" button
  hint: 'It is a question: "who am I".',    // appears after 2 misses
  out: 'student',                           // what the terminal prints
  what: 'who am I?',                        // end-of-session command log
  why: 'Always know whose rights you are using.'
}
```

Useful extras: `partial: [{ re, msg }]` gives specific coaching for a close-but-wrong command, a `note` on an accepted variant shows a remark, and `{host}` in `out` prints the station name.

### Keep it honest

- Accepted answers are regular expressions, so a student typing `ls -la` for `ls -l` can still pass if you allow it. Reject anything that changes more than the mission asks.
- Outputs are realistic, not captured from a real machine. Check the firewall and service commands against your own practice image.
- The 12/11 entry is a rest day (`rest: '...'`) with no screens.
