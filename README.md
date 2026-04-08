# Karmê Chöling — Mockup Site

A working mockup of a redesigned Karmê Chöling website. Four pages, all static HTML, hosted on GitHub Pages. Edit any page with Claude and the live site updates in under a minute.

## The Pages

| File | What it is | Live URL |
|---|---|---|
| `index.html` | Homepage — the three hubs | `/` |
| `heal.html` | Rest & Heal — six healing programs | `/heal.html` |
| `learn.html` | Learn to Meditate — three beginner doors | `/learn.html` |
| `retreat.html` | Go on Retreat — three retreat lengths | `/retreat.html` |

All four files live in the root of this repo. Each file is self-contained — the CSS, HTML, and content are all in one place. Nothing else to install, nothing else to wire up.

**Repository:** https://github.com/esuchocki/site-mock
**Live preview:** https://esuchocki.github.io/site-mock/index.html

---

## How to Edit a Page with Claude

This is the whole workflow. Seven steps, no command line, no Git knowledge needed.

1. **Open the file on GitHub.** Go to this repo on github.com and click the file you want to change (for example, `heal.html`).
2. **Click the pencil icon** in the top-right of the file view. It says "Edit this file" when you hover. This opens GitHub's built-in editor in your browser.
3. **Select all the text** in the editor (Cmd+A on Mac, Ctrl+A on Windows) and copy it (Cmd+C / Ctrl+C).
4. **Open Claude** in a new browser tab and start a new chat. Paste the entire file into the chat, then describe what you want to change. Examples:
   - *"Change the headline from 'A place to stop.' to 'A place to land.'"*
   - *"Add a seventh program card for a new 'Grief and Loss' weekend retreat. Use a simple geometric icon. Keep the same style as the other cards."*
   - *"Make the teaching quote paragraph a little shorter — keep the first two sentences and drop the rest."*
5. **Copy Claude's response.** Claude will return the full updated file. Copy all of it.
6. **Paste it back into the GitHub editor**, replacing everything that was there. Scroll to the bottom.
7. **Commit the change.** Under "Commit changes," write a short message describing what you did (e.g., *"Update Rest & Heal headline"*) and click the green **Commit changes** button. That's it.

The live site updates automatically within about 30 seconds. Refresh the live URL in your browser to see it.

---

## A Few Guardrails

**Always paste the whole file into Claude.** Don't paste snippets. Claude needs to see the full file to maintain the consistent styling across all four pages.

**Tell Claude what page you're working on.** Start your prompt with something like *"This is the Rest & Heal page from a four-page mockup site for Karmê Chöling. The design system uses Literata, white background, orange (#f16739) and teal (#4fcca0) accents. Here's the current file:"* — this keeps Claude aligned with the existing aesthetic.

**Ask Claude to keep the existing structure.** Say *"preserve the layout and CSS, only change the content I asked about"* when you want a small change. Claude will sometimes try to improve things you didn't ask it to touch; this phrase holds it in place.

**If something breaks, undo.** Every commit creates a snapshot you can return to. On GitHub, click the **History** button at the top of any file to see previous versions and click one to restore it.

**For edits that need real information, tell Claude to research.** When you want to add new programs, teacher bios, current dates, or any factual content that isn't already on the page, explicitly ask Claude to research karmecholing.org before writing. Example: *"Research what beginner programs Karmê Chöling currently offers on karmecholing.org and replace the three cards with the three most appropriate real programs."* Without the word "research" and a named source, Claude will guess from general knowledge and sometimes invent plausible-sounding programs that don't actually exist at KCL. The word "research" flips Claude into a different mode where it looks things up instead of generating from memory.

**Test locally (optional).** You don't need to do this, but if you want to preview changes before committing: save the file to your desktop, open it in your browser. Everything works as a standalone file.

---

## Making a New Page

If you want to add a new page (say, a "Community" hub or a teacher bio page), the easiest path is:

1. Open one of the existing hub pages (heal.html is a good starting point — it has the richest layout).
2. In GitHub, click **Copy raw file** (or select all, copy the content).
3. Create a new file in the repo: click **Add file → Create new file**, name it something like `community.html`, and paste the content.
4. Open Claude, paste the file, and say: *"Transform this into a Community hub page for Karmê Chöling. The teaching should be about sangha and belonging. Replace the six program cards with four community offerings. Keep the visual style identical."*
5. Commit. The new page is live at `/<new-filename>.html`.
6. **Don't forget to link to it.** Open each existing page, find the `<nav>` section near the top, and add a link so visitors can reach the new page. Claude can do this for you — just paste the file and say *"add 'Community' as a fourth nav link pointing to community.html."*

---

## What's NOT Here Yet

These are intentional gaps. The mockup is meant to show the design direction and content architecture — it does not include:

- **Program listings** with real dates, prices, or registration. The "Find a place to rest/begin/settle" links at the bottom of each hub page currently go nowhere.
- **Individual program detail pages.** The six program cards on the Rest & Heal page link to `#` — the detail pages haven't been built yet.
- **A working contact form, donation flow, or mailing list signup.** The footer links (Visit, Contact, Donate) are placeholders.
- **Images or photography.** The icons are hand-drawn SVG line art. No photos yet — that's a deliberate choice for the mockup phase and a real design decision for later.
- **A backend.** This is pure static HTML. When the real site launches, it will connect to the KCL engine for dynamic program data. For now, everything is hand-edited content.

Every one of these is intentional for the mockup stage. As you iterate on the design and content with Claude, none of the missing pieces need to be in place.

---

## Design System (for Claude)

If you ever want to start a fresh Claude chat and keep it oriented, paste this block as context:

> This is a mockup site for Karmê Chöling, a residential meditation retreat center in Barnet, Vermont, founded in 1970 as the first Western seat of the Shambhala Buddhist lineage. The site has four pages: a homepage (three hubs: Rest & Heal, Learn to Meditate, Go on Retreat) and three hub pages, one per door. The design system is: Literata serif throughout, white background, orange (#f16739) as the primary accent, teal (#4fcca0) reserved for the Rest & Heal page, ink (#1c1c1a) for text. Generous whitespace. Hairline rules (not boxes) for visual separation. Custom line-art SVG icons at 1.25px stroke weight. Subtle staggered fade-up animations on page load. The tone is contemplative, plain English, no Sanskrit or Tibetan terminology. Each hub page has a consistent structure: centered hero (eyebrow → headline → italic teaching), a "place" statement, a grid of offerings, and a single closing link.

Paste that plus the current file, and Claude will stay in the right register.

---

## Getting the Repo Set Up (One-Time, for the Developer)

*Skip this section if it's already been done.*

1. Create a new public repo on GitHub (any name, e.g., `kcl-mockup`).
2. Upload the four HTML files and this README to the repo root (drag-and-drop works in the GitHub web UI).
3. Go to **Settings → Pages**. Under "Build and deployment," set **Source** to "Deploy from a branch" and **Branch** to `main` / `/ (root)`. Click **Save**.
4. Wait about a minute, then visit `https://<your-username>.github.io/<repo-name>/`. The homepage should load.
5. Update the "Live preview" URL at the top of this README so the Marketing Director knows where to look.

That's it. From that point on, everything happens through the GitHub web editor and Claude.
