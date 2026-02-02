# CAD Payment Links

Simple static page for partners to copy Stripe payment links (CAD 100–1500) and share with clients. No backend; hosted on GitHub Pages.

## 1. Add your Stripe links

Open **index.html** and find the `PAYMENT_LINKS` object in the `<script>` section. Replace each placeholder URL with your real Stripe payment link for that amount:

```javascript
const PAYMENT_LINKS = {
  100:  'https://buy.stripe.com/your_actual_link_100',
  200:  'https://buy.stripe.com/your_actual_link_200',
  // ... up to 1500
};
```

Save the file when done.

---

## 2. Try it locally before deploying

### Option A – Open the file in the browser

1. In File Explorer, go to the `Payment LInks` folder.
2. Double‑click **index.html** to open it in your default browser.
3. You’ll see the price list and Copy buttons. Copy will work; the links will be whatever you put in `PAYMENT_LINKS`.

### Option B – Use a local server (recommended)

Some browsers restrict clipboard when the page is opened as `file://`. If “Copy” doesn’t work, use a tiny local server:

1. Open **PowerShell** or **Command Prompt**.
2. Go to the project folder:
   ```bash
   cd "C:\Users\thepr\Desktop\Payment LInks"
   ```
3. If you have **Python** installed:
   ```bash
   python -m http.server 8080
   ```
   Or with **Node.js** (if you have `npx`):
   ```bash
   npx serve -l 8080
   ```
4. In your browser, open: **http://localhost:8080**
5. Test the Copy buttons. When finished, press `Ctrl+C` in the terminal to stop the server.

---

## 3. Deploy on GitHub Pages

**Step 1 – Create a repo on GitHub**

- Go to [github.com/new](https://github.com/new).
- Pick a name (e.g. `payment-links`).
- Leave “Add a README” unchecked (you already have files).
- Click **Create repository**.

**Step 2 – Push your project**

In PowerShell (or Terminal), from your project folder:

```powershell
cd "C:\Users\thepr\Desktop\Payment LInks"
git init
git add index.html README.md
git commit -m "Payment links page"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your GitHub username and `YOUR_REPO_NAME` with the repo name you chose (e.g. `payment-links`). If Git asks for login, use your GitHub username and a **Personal Access Token** as the password (not your normal GitHub password).

**Step 3 – Turn on GitHub Pages**

- Open your repo on GitHub.
- Go to **Settings** → **Pages** (left sidebar).
- Under **Build and deployment** → **Source**, choose **Deploy from a branch**.
- Under **Branch**, choose **main** and **/ (root)**.
- Click **Save**.

**Step 4 – Open your site**

After 1–2 minutes your site will be live at:

**`https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`**

Example: if your username is `jane` and the repo is `payment-links`, the URL is  
`https://jane.github.io/payment-links/`

Share that link with your partners so they can copy and share payment links with clients.
