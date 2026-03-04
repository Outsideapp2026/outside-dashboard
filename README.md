# Outside Dashboard 🌃

> **Toronto Nightlife Business Dashboard** — Track revenue, manage bookmarks, monitor venues, and generate weekly reports. Works on desktop and mobile.

**Live URL (after Vercel deploy):** `https://outside-dashboard.vercel.app`

---

## 📋 What It Does

| Feature | Description |
|---------|-------------|
| 📊 **Overview** | Revenue, profit, orders, downloads — KPI cards + charts |
| 🔖 **Bookmarks** | View, add, edit, delete, search, filter, import/export your bookmarks |
| 🌙 **Nightlife** | Venue table, booking stats, social-to-download funnel |
| 📝 **Reports** | Generate & download weekly business reports as .txt files |

---

## 🚀 How to Run It

### Option 1: Run Locally (No Installation Needed)

1. Download `index.html` from this repo
2. Double-click the file to open it in your browser
3. That's it — no server, no terminal, no build step needed ✅

### Option 2: Deploy to Vercel (Recommended — Works on Phone!)

**Step 1: Fork or clone this repo**

```bash
git clone https://github.com/Outsideapp2026/outside-dashboard.git
cd outside-dashboard
```

**Step 2: Go to [vercel.com](https://vercel.com)**
- Sign up / log in
- Click **"New Project"**
- Click **"Import from GitHub"**
- Select **`outside-dashboard`** from your repos

**Step 3: Configure the project**
- Framework Preset: **Other** (leave blank)
- Root Directory: `./` (default)
- Build Command: leave blank
- Output Directory: leave blank

**Step 4: Deploy!**
- Click **Deploy** — it'll be live in ~30 seconds
- Your URL will be: `https://outside-dashboard.vercel.app`

> **Note:** If that name is taken, Vercel will assign you a unique URL like `outside-dashboard-abc123.vercel.app`

---

## 📱 How to View on Your Phone

After deploying to Vercel:

1. **Open Safari or Chrome on your phone**
2. **Go to your Vercel URL** (e.g. `https://outside-dashboard.vercel.app`)
3. **Add to Home Screen** for an app-like experience:
   - **iPhone/Safari:** Tap the Share button → "Add to Home Screen"
   - **Android/Chrome:** Tap the three-dot menu → "Add to Home Screen"

The dashboard is fully **mobile-responsive** — all tabs, charts, and bookmark management work on any screen size.

---

## 📅 How to Get Weekly Reports

### Option 1: Manual (Simplest)
1. Open the dashboard (phone or desktop)
2. Go to the **Reports** tab
3. Click **"Download Weekly Report (.txt)"**
4. A `.txt` file downloads to your device with full stats + bookmark summary

### Option 2: Phone Reminder (Recommended)
- Set a recurring alarm every **Monday morning**
- When it fires, open the dashboard URL and tap "Download Weekly Report"

### Option 3: GitHub Actions (Automated)

Add this file to your repo as `.github/workflows/weekly-report.yml`:

```yaml
name: Weekly Report Reminder

on:
  schedule:
    - cron: '0 9 * * 1'  # Every Monday at 9am UTC

jobs:
  notify:
    runs-on: ubuntu-latest
    steps:
      - name: Send reminder
        run: |
          echo "Weekly report reminder: Visit your dashboard to download your report"
          echo "URL: https://outside-dashboard.vercel.app/#reports"
```

> For email delivery, add your email provider's API key as a GitHub Secret and use a send-email action.

---

## 🔖 Bookmark Manager Guide

### Viewing Bookmarks
- Go to the **Bookmarks** tab
- Use **Search** to find by name, URL, or notes
- Filter by **Category** or **Folder**
- Toggle between **Grid** and **List** view

### Adding a Bookmark
1. Click **"+ Add"**
2. Fill in: Name, URL, Category, Folder, Status, Notes
3. Click **"Add Bookmark"**
4. It saves automatically to your browser (localStorage)

### Editing a Bookmark
1. Find the bookmark in the list
2. Click **"Edit"**
3. Modify any field
4. Click **"Save Changes"**

### Deleting a Bookmark
- Click **"×"** on any bookmark → confirm the dialog

### Importing Bookmarks
- Click **"📥 Import"**
- Paste JSON in this format:
```json
[
  {
    "name": "My Site",
    "url": "https://example.com",
    "category": "Work",
    "folder": "Tools",
    "status": "active",
    "notes": "Main work tool"
  }
]
```
- Click **Import**

### Exporting Bookmarks
- Click **"📤 Export"** to download a `outside-bookmarks-YYYY-MM-DD.json` file
- Use this as a backup or to transfer to another device

> **Note:** Bookmarks are stored in your browser's localStorage. They persist between sessions on the same device/browser. Export regularly as backup!

---

## 📁 File Structure

```
outside-dashboard/
├── index.html      # Complete self-contained dashboard (no build needed)
├── vercel.json     # Vercel deployment config
└── README.md       # This file
```

---

## 🛠 Tech Stack

- **React 18** (loaded from CDN)
- **Recharts** (charts — loaded from CDN)
- **Tailwind CSS** (loaded from CDN)
- **Babel Standalone** (JSX compiled in-browser)
- **localStorage** (bookmark persistence)
- **No build step** — open index.html directly in any browser

---

## 🔧 Customizing Your Data

To change the default data (venues, weekly numbers, etc.), edit `index.html` and look for the sections marked:

```javascript
// ============ DEFAULT DATA ============
const DEFAULT_BOOKMARKS = [...];
const WEEKLY_DATA = [...];
const VENUES = [...];
```

---

## 📞 Support

Built for **Outside** — Toronto's premier nightlife platform. 🌙

Questions? Open an issue on this repo.
