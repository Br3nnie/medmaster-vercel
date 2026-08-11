# MedMaster — Deploy to Vercel 

## What's in this folder

```
medmaster-vercel/
  api/
    chat.js          ← serverless proxy (keeps your API key private)
  public/
    index.html       ← the app
  vercel.json        ← routing config
  README.md
```

---

## Deploy in 5 steps

### 1. Get a free Vercel account
Go to https://vercel.com and sign up (free tier is fine).

### 2. Install the Vercel CLI
```bash
npm install -g vercel
```

### 3. Deploy
In your terminal, navigate to this folder and run:
```bash
cd medmaster-vercel
vercel
```
Follow the prompts:
- Set up and deploy? **Y**
- Which scope? Choose your account
- Link to existing project? **N**
- Project name: `medmaster` (or anything you like)
- In which directory is your code? **./public** → type `.` and press enter for root
- Override settings? **N**

### 4. Add your Anthropic API key
After the first deploy, go to:
**Vercel Dashboard → Your Project → Settings → Environment Variables**

Add:
- **Name:** `ANTHROPIC_API_KEY`
- **Value:** your key from https://console.anthropic.com
- **Environments:** Production, Preview, Development

### 5. Redeploy to pick up the key
```bash
vercel --prod
```

Your app will be live at `https://medmaster-xxxx.vercel.app`

---

## Add to iPhone home screen
1. Open the URL in **Safari**
2. Tap the Share button (box with arrow)
3. Tap **"Add to Home Screen"**
4. Tap **Add**

It will appear as a full-screen app with no browser chrome.

---

## Update the app
Edit `public/index.html` locally, then run:
```bash
vercel --prod
```

---

## Anthropic API key
Get yours at: https://console.anthropic.com/keys
The key is only stored in Vercel's encrypted environment — never in the HTML file.
