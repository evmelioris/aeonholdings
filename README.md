# Aeon Holdings — website

A single self-contained page. No build step, no frameworks, no external
dependencies. Just static files you can drop onto any host.

## Files

| File            | What it is                                                        |
| --------------- | ----------------------------------------------------------------- |
| `index.html`    | The entire website — text, styling, and behavior are all in here. |
| `og-image.png`  | The preview image shown when the link is shared or texted (1200×630). |
| `og-image.svg`  | The editable source for that preview image (optional to keep).    |

---

## Editing the text later (no coding needed)

Open `index.html` in any plain-text editor (even TextEdit). All the wording is
plain sentences between the tags. To change a headline or paragraph, just edit
the words and leave the `<...>` tags around them alone, then save.

Common edits:
- **Email address** — search the file for `evan@aeonholdings.co` and replace
  every instance if it ever changes.
- **Headline / paragraphs** — find the sentence you want and type over it.
- **Add a real photo of Evan** — put a photo named `evan.jpg` next to
  `index.html`. In the file, find the block labeled `Replace this placeholder
  with a photo` (in the About section) and follow the one-line instructions
  there: swap the gray placeholder `<div>` for the `<img>` line that is already
  written out in the comment.
- **SEO title / description** — near the top of the file, under the comment
  `SEO — edit the title and description below`.

Save the file, re-upload it (or re-drag the folder if using Netlify), and the
site updates.

---

## Publishing it (pick one — all are free)

### Option A — Netlify (easiest, drag-and-drop)
1. Go to <https://app.netlify.com/drop>.
2. Drag the whole `aeonholdings-site` folder onto the page.
3. It goes live instantly on a temporary `...netlify.app` address.
4. To use `aeonholdings.co`, open **Site settings → Domain management → Add a
   custom domain**, enter `aeonholdings.co`, and follow the DNS step below.

### Option B — Vercel
1. Create a free account at <https://vercel.com>.
2. **Add New → Project**, and either drag the folder in or connect a Git repo.
3. Add `aeonholdings.co` under **Settings → Domains**, then do the DNS step.

### Option C — GitHub Pages
1. Create a repository and upload these files to it.
2. **Settings → Pages → Deploy from branch**, choose `main` / root.
3. Add `aeonholdings.co` under the **Custom domain** field, then the DNS step.

---

## Pointing aeonholdings.co (registered at Namecheap) to the host

You do this once, in the Namecheap dashboard. Your host (Netlify/Vercel/GitHub)
will show you the exact target values when you add the domain — use theirs if
they differ from the examples below.

1. Log in to Namecheap → **Domain List** → **Manage** next to `aeonholdings.co`.
2. Open the **Advanced DNS** tab.
3. Remove the default Namecheap "parking" records (the CNAME to
   `parkingpage.namecheap.com` and any placeholder A record).
4. Add the records your host asks for. Typical values:

   **Netlify**
   - Type `A` — Host `@` — Value `75.2.60.5`
   - Type `CNAME` — Host `www` — Value `<your-site>.netlify.app`

   **Vercel**
   - Type `A` — Host `@` — Value `76.76.21.21`
   - Type `CNAME` — Host `www` — Value `cname.vercel-dns.com`

   **GitHub Pages**
   - Type `A` — Host `@` — Values `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153` (add all four)
   - Type `CNAME` — Host `www` — Value `<your-username>.github.io`

5. Save. DNS changes can take anywhere from a few minutes to a few hours.
6. Back in your host's dashboard, enable **HTTPS / SSL** (it's usually
   automatic and free once the domain resolves).

That's it — `https://aeonholdings.co` will serve this page.

---

## Notes

- **The contact form** composes a pre-filled email in the visitor's own mail app
  and sends it to `evan@aeonholdings.co`. It needs no server, which is why it
  works on any static host. The email address is also shown plainly above the
  form so anyone can reach out directly.
- **Everything is honest and current**: the copy describes Evan as an individual
  buyer at the start of his search. There is no invented track record — keep it
  that way as you edit.
