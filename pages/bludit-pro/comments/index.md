# Comments
<!-- position: 3 -->

A native, self-hosted comment system for your Bludit site. No third-party service, no tracking, no external database — all comments are stored as flat JSON files inside your Bludit workspace.

- **Guests** can post comments, which land in a moderation queue for you to approve.
- **Admins and editors** can post comments that are published immediately.
- Built-in anti-spam gates (honeypot, time check, link limit, spam words) with optional Cloudflare Turnstile for public sites.

Comments is included in Bludit PRO, but you can buy it separately from here:
- https://plugins.bludit.com/plugin/comments

---

<h2 id="installing-and-enabling">Installing and enabling</h2>

1. Copy the plugin folder into `bl-plugins/comments/`.
2. Go to **Admin → Plugins** and click **Activate** on "Comments".
3. Click the plugin's **Settings** to configure it (see below).
4. Comments now render automatically at the bottom of any eligible page.

A "Comments" entry is also added to the admin sidebar — that's your moderation queue.

---

<h2 id="where-comments-appear">Where comments appear</h2>

You control which content types get the comment form:

| Setting | What it does |
|---|---|
| **Enable on pages** | Show the form on regular published pages. |
| **Enable on static pages** | Show the form on static pages (About, Contact, etc.). |
| **Enable on sticky pages** | Show the form on sticky/pinned pages. |

Each Bludit page also has its own per-page toggle (the "Allow comments" switch in the page editor). If you turn that off on a specific page, the plugin skips it regardless of the plugin-level settings above.

---

<h2 id="settings-reference">Settings reference</h2>

### Display

| Setting | What it does | Default |
|---|---|---|
| **Comments per page** | How many approved comments to show before paginating. | 20 |
| **Sort order** | Newest-first or oldest-first. | Newest first |
| **Maximum comment length** | Hard cap on comment body length (characters). Longer submissions are rejected. | 5000 |
| **Close comments after N days** | Hides the comment form on pages older than N days. Existing comments remain visible. `0` = never close. | 0 |

### Moderation & notifications

| Setting | What it does | Default |
|---|---|---|
| **Email notification on new pending comment** | Sends an email to the admin whenever a guest submits a comment that needs review. | Enabled |
| **Notification email** | Where to send those emails. Leave blank to use the site's default "from" address. | *(blank)* |

### Bot protection

These are all free, built-in, and work without any external service. Leave them on unless you have a specific reason to disable them.

| Setting | What it does | Default |
|---|---|---|
| **Enable honeypot field** | Adds an invisible decoy input. Humans leave it empty; naïve bots fill it and get rejected. Zero UX cost. | Enabled |
| **Enable time-based submission check** | Rejects submissions that arrive faster than the configured minimum — bots usually POST instantly, humans take seconds. | Enabled |
| **Minimum seconds before submit** | The threshold used by the check above. Below this, the submission is rejected. | 3 |
| **Maximum links per comment** | Rejects comments containing more than N links (`http://` or `https://`). Spam comments typically have many. Set to `0` to disallow links entirely. | 2 |
| **Spam words** | One per line. Any comment whose text contains one of these words (case-insensitive) is rejected. | *(empty)* |

### Cloudflare Turnstile (optional CAPTCHA)

Recommended for public sites; not needed on localhost or private intranets.

| Setting | What it does |
|---|---|
| **Enable Cloudflare Turnstile** | Adds a Turnstile challenge to the **guest** form. Logged-in users skip it. |
| **Site key** | Public Turnstile key (appears in the rendered widget). |
| **Secret key** | Private Turnstile key (used server-side to verify the token). |

Create free Turnstile keys at [dash.cloudflare.com → Turnstile](https://dash.cloudflare.com/?to=/:account/turnstile).

---

<h2 id="moderation-queue">The moderation queue</h2>

Open **Admin → Comments** to see the queue. It has four tabs:

- **Pending** — guest comments awaiting your review. Approve to publish, move to spam/trash, or delete.
- **Approved** — currently-published comments.
- **Spam** — comments you flagged as spam. You can still approve or delete from here.
- **Trash** — soft-deleted comments. Restore or permanently delete.

Each row shows the author, excerpt, page, and date, plus per-comment action buttons. Use the **Bulk actions** dropdown above the table to approve / spam / trash / delete many comments at once.

A badge with the pending count appears next to **Comments** in the sidebar, and a reminder widget shows up on the dashboard whenever there's something to review.

---

<h2 id="blocked-ips">Blocked IPs</h2>

From the moderation page, click **Blocked IPs** (top-right of the tabs). You can:

- Manually add an IP address to block it from submitting new comments.
- Remove an IP to unblock it.

IPs are stored as hashes, not plaintext, for privacy. You enter a normal IP address — the plugin hashes it before saving.

---

<h2 id="guest-vs-logged-in-experience">Guest vs logged-in experience</h2>

### Guests (anonymous visitors)

- See name, email, and comment fields.
- Their comments land as **pending** and are invisible until you approve them.
- After submitting, they see a *"Thanks! Your comment is awaiting moderation."* message instead of the form. Refreshing the page brings the form back.
- All bot protections (honeypot, time check, link limit, spam words, Turnstile) apply.

### Admins and editors (logged in)

- See no name/email fields — just the comment textarea and a small "Posting as [your name]" hint.
- Comments are **published immediately** (no moderation).
- Bot protections are skipped (you're already authenticated).
- The name and email on the published comment come from the user profile, not from any form input — so tampering client-side does nothing.
- A small badge ("Admin" or "Editor") is shown next to the author name on published comments.

---

<h2 id="privacy">Privacy</h2>

The plugin is privacy-minded by default:

- No third-party services are called unless you explicitly enable Turnstile.
- IP addresses are **hashed** (SHA-256 with a per-install secret) before being stored with comments or in the blocklist — the raw IP is never written to disk.
- User-Agent strings are hashed the same way.
- Email addresses are stored (needed for admin-notification replies) but never rendered on the public page.

---

<h2 id="troubleshooting">Troubleshooting</h2>

**The form doesn't appear on a page.**
Check the per-page "Allow comments" toggle in the page editor, and the corresponding "Enable on …" setting in the plugin. Also check "Close comments after N days" — if the page is older than that, the form is hidden.

**A legitimate user got rejected.**
Check the Bludit log file (`bl-content/debug.txt`). Rejections are logged with a reason like `honeypot-filled`, `too-fast`, `too-many-links`, `spam-word`, or `turnstile-failed`. Adjust the corresponding setting.

**Email notifications aren't arriving.**
Confirm the site has a working email "from" address (Admin → Settings → Email). If "Notification email" is blank, the plugin uses the site default. Emails are sent via PHP `mail()` — if your host doesn't support it, nothing will arrive.

**Guest posts a comment but the form keeps showing.**
Browser cookies are required. The plugin uses a short-lived `bludit_comment_pending` cookie to hide the form on the page right after submission. If cookies are blocked, the form will still appear (the comment was still stored).

---

<h2 id="uninstalling">Uninstalling</h2>

Deactivate the plugin from **Admin → Plugins**. Your comment data in `bl-content/workspaces/comments/` is **not** deleted automatically — remove that folder manually if you want to wipe all comment history.
