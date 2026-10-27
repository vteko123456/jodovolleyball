# Our team hub

This repository holds our team's data for [TMT: Volleyball Hub](https://github.com/KagazzIe/TMT-VolleyballHub):
our team name and roster, our rotation positions, and our tagged match clips. GitHub turns it into
our team's website automatically.

Your site's address is `https://OWNER.github.io/THIS-REPOSITORY-NAME/`, where OWNER is your GitHub
name, or the organization's name if this repository belongs to a GitHub organization.
You can also find it under **Settings → Pages**.

Everything in this repository is public. Anyone with the link can see the site.

## What's in here

| File | What it is | Where it comes from |
|---|---|---|
| `team.json` | Team name, player list, play labels (Serve, Receive, your own…) and clip tags (like Good, Bad) | The hub's **Team Setup** page |
| `rotations.json` | Your rotation positions, highlights and notes | The hub's **5-1 Rotation Guide** → Edit positions → Save to GitHub (or Export JSON) |
| `clips/` | One file per match | The hub's **Clip Marker** → Save to GitHub (or Download JSON) |
| `.github/workflows/deploy.yml` | Builds your site. You don't need to touch it. | Came with this repository |

## Updating your site

### The quick way: Save to GitHub

Team Setup, the rotation guide's editor and Clip Marker each have a **Save to GitHub** button.
It saves the file straight into this repository, so you don't have to download and upload anything.

The first time you click it, your hub asks you to connect:

1. Click **Open GitHub's new token page**. GitHub opens a form with most of it filled in.
2. Under **Repository access**, choose **Only select repositories** and pick this repository.
3. Click **Generate token**, copy the token, paste it into your hub, and click **Connect**.

That's it. Your hub remembers the token until you close the tab, or on this device if you check
**Remember on this device** (leave that off on shared computers). The token can only change files in
this repository, and it expires after a year. To stop using it, click **Disconnect** under the Save
button, or delete it on GitHub under **Settings → Developer settings → Personal access tokens**.

Only this repository's owner can make the token, unless the repository belongs to a GitHub
organization. Anyone else can still use the upload way below, or see
[Letting several people save](#letting-several-people-save).

### The upload way

Download a file from your hub, then upload it here.

1. Make the change on your hub site and download the file.
2. Open this repository on GitHub. For a match file, click into the **clips** folder first.
3. Click **Add file → Upload files** and drag the file in. A file with the same name gets replaced.
4. Click **Commit changes**.

Your site updates about two minutes later. To watch, open the **Actions** tab: a yellow dot means
it's working, a green check means it's done. If the page still looks old, refresh it with
**Ctrl+F5** (Windows) or **Cmd+Shift+R** (Mac).

## Letting several people save

GitHub only lets other people make a Save to GitHub token for a repository that belongs to an
**organization**. Organizations are free, and you stay in charge: you choose who can save, and you can
approve or cancel each person's token. If your repository is under your own account, move it into an
organization once. Your site's address changes to `https://ORGANIZATION.github.io/THIS-REPOSITORY-NAME/`.

### 1. Create the organization (you, once)
1. Open [GitHub's new organization page](https://github.com/account/organizations/new?plan=free) and
   choose the **Free** plan.
2. Pick a short name, like `team-name-volleyball`. It becomes the start of your site's address.
3. Enter your email, choose **My personal account**, and finish.

### 2. Choose how tokens are allowed (you, once)
In the organization, open **Settings**, then **Personal access tokens → Settings** (under "Third-party Access"):
1. **Fine-grained tokens:** choose **Allow access via fine-grained personal access tokens**, and
   **Require administrator approval**. Click **Save**.
2. **Personal access tokens (classic):** choose **Restrict access via personal access tokens (classic)**.
   Click **Save**.

Also check **Settings → Actions → General** says **Allow all actions and reusable workflows**, so your
site can still build.

### 3. Move this repository into the organization (you, once)
Skip this if you made the repository in the organization to begin with.
1. In this repository, open **Settings**, scroll to the bottom, and click **Transfer ownership**.
2. Choose your organization, type the repository's name, and confirm.
3. Open **Settings → Pages** and make sure **Source** says **GitHub Actions**.
4. Open **Actions → Deploy team hub → Run workflow** and click the green button. After about two
   minutes, your site is at its new address. The old address stops working, so share the new one.

Your own Save to GitHub token stops working after the move. Click Save to GitHub on the new site and
connect again; the token page now picks the organization for you.

Finish or save any Clip Marker game in progress before you move: your browser keeps unsaved work
per site address, so the new address starts empty.

### 4. Add your helpers
1. Organization **Settings → Member privileges → Base permissions**: choose **Read**, so people can
   only save to repositories you pick.
2. **People → Invite member**: invite each helper by GitHub name or email, as a **Member**. They
   need a free GitHub account and must accept the email invitation.
3. **Teams → New team**: call it something like `Taggers`, and add your helpers to it.
4. In the team, open **Repositories → Add repository**, pick this repository, and give it **Write**.

### 5. Helpers connect, you approve
1. Each helper opens your site, clicks **Save to GitHub**, and follows the same steps as above.
   The token page already chooses the organization; they pick this repository under
   **Repository access**.
2. You get an email. Open organization **Settings → Personal access tokens → Pending requests**,
   check the request is for this repository only, and click **Approve**. Until then, their saves say
   the token can't change files.
3. To take away someone's access, open **Personal access tokens → Active tokens** and revoke their token,
   or remove them from the team.

### When two people edit the same game
Clip Marker remembers which version of a game you opened. If someone else saved that game on GitHub
since then, Save to GitHub asks before replacing it, and says how many clips each version has. Choose
**Cancel** to keep both: click **Download JSON** to keep your version, then **Open** the newer game and
add your clips to it. Easiest is to split the work so each person tags different games.

## If something goes wrong

- **Red X in the Actions tab:** click it to see which step failed. The most common cause is the
  setting below.
- **The site shows this text instead of the hub:** go to **Settings → Pages** and make sure
  **Source** says **GitHub Actions**, not "Deploy from a branch". Then open **Actions → Deploy team hub →
  Run workflow** and click the green button.
- **Save to GitHub says the token can't see or change this repository:** make a new token on GitHub's
  token page, and make sure you pick this repository under **Repository access**. If this repository
  belongs to an organization, you also need Write access to it, and an owner may need to approve
  your token first.
- **A grey icon on the very first run:** that's expected. The first run is skipped because
  GitHub Pages isn't switched on yet at that moment.
