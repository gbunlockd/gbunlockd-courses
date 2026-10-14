# GBUnlockd list

One page, two tabs: **📚 Courses** and **💸 Resell**.

| File | What it is |
|---|---|
| `index.html` | The page. You never edit this. |
| `courses.json` | The courses tab. |
| `resell.json` | The resell tab — subscriptions. |
| `logo.png` | Your logo. Optional. |

---

## Updating the repo you already have

**Add file → Upload files**, drag in `index.html` and `resell.json`, **Commit
changes**.

> **Leave `courses.json` alone.** Your real courses are in it. Uploading the
> one from this folder would wipe them.

The site is live again within a minute.

---

## The two links

Same page, two addresses:

```
Courses   https://gbunlockd.github.io/gbunlockd-courses/
Resell    https://gbunlockd.github.io/gbunlockd-courses/#resell
```

Whichever one they open, they land on that tab — and they can tap the other
tab to cross over. Both go in `.env`:

```
COURSES_URL=https://gbunlockd.github.io/gbunlockd-courses/
RESELL_URL=https://gbunlockd.github.io/gbunlockd-courses/#resell
```

---

## Adding something

Open `courses.json` or `resell.json` in the repo → the **pencil** → add a
block → **Commit changes**.

```json
{
  "name": "The name",
  "category": "Marketing",
  "full": 997,
  "cost": 45,
  "link": "https://the-official-page.com",
  "note": "Anything you want people to know."
}
```

| Field | Needed? | What it is |
|---|---|---|
| `name` | **yes** | What members see. No name, and the row is skipped. |
| `category` | no | Groups it, and adds it to the dropdown. |
| `full` | no | The normal price, shown struck through. Leave it out and no saving is shown. |
| `cost` | **yes** | **What the member pays you.** The big number. |
| `link` | no | The official page. |
| `note` | no | Anything. Use `\n` for a new line. |

`link` and `note` are the two things folded behind the arrow. A row with
neither has no arrow — it just doesn't open.

Both files take exactly the same fields. The only difference is the name of
the list inside: `"courses": [...]` in one, `"resell": [...]` in the other.
Don't swap those around.

### Rules that will bite you

- Every entry except the last needs a **comma after its closing `}`**.
- The last one must **not** have a comma.
- Prices are plain numbers: `45`, not `"$45"` and not `"45"`.
- Quotes must be straight `"`. Pasting from Word or Notes can give you curly
  ones, and then the tab shows *"Back in a moment"*.

If a tab says that, its JSON is broken. Paste the file into
[jsonlint.com](https://jsonlint.com) and it points at the line. The other tab
keeps working — the two files are loaded separately.

---

## Things worth knowing

**Delete the three EXAMPLE rows** in `resell.json` before you post the link.

**`updated` at the top** of each file is just text in the footer. Each tab
shows its own.

**Opening `index.html` from your computer won't work** — it needs a real web
address to load the lists. Test on the GitHub Pages link.

**An empty tab is fine.** If `resell.json` isn't uploaded yet, the resell tab
says "Nothing here yet" and the courses tab is unaffected.

---

## Posting it in Discord

The panels carry the links themselves once `COURSES_URL` and `RESELL_URL` are
set — `/courses_panel` and `/resell_panel`. If you also want it in a plain
channel:

```
/msg channel:#courses
```

> **📚 Everything we have**
> Courses: https://gbunlockd.github.io/gbunlockd-courses/
> Apps and subscriptions: https://gbunlockd.github.io/gbunlockd-courses/#resell
> You pay the Cost price. Open a ticket and say which one you want.

`/msg_edit` changes that message later without deleting it, so the links only
ever get posted once.
