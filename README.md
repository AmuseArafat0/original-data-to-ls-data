# ⚡ Zoom CSV Converter

A lightweight, browser-based tool to convert raw Zoom webinar CSVs into Exotel-ready format — no server, no dependencies, runs 100% in your browser.

## 🔄 What it does

| Input Column | Output Column | Transformation |
|---|---|---|
| `Phone` + `CountryCode` | `Phone` | `'+91-XXXXXXXXXX` format |
| `emailid` | `emailid` | Passed through as-is |
| `zoomads` (suffix) | `zoomads` | Prefixed with full Zoom URL |
| `zoomid` | `zoomid` | Cleaned numeric meeting ID |

**Example:**

| Before | After |
|---|---|
| Phone: `6289572538`, CountryCode: `91` | `'+91-6289572538` |
| zoomads: `WN_REV6WJ5hTNa85OQwB1EnNQ` | `https://zoom.us/webinar/register/WN_REV6WJ5hTNa85OQwB1EnNQ` |

## 🚀 Usage

1. Open `index.html` in any browser (Chrome, Edge, Firefox)
2. Set the Zoom Webinar base URL (default: `https://zoom.us/webinar/register/`)
3. Optionally override Zoom Webinar ID and Meeting ID
4. Upload your original CSV file
5. Preview the first 5 converted rows
6. Click **Convert & Download** — get your converted CSV instantly

## 📁 Publishing on GitHub Pages

1. Create a new GitHub repository
2. Upload `index.html` to the root
3. Go to **Settings → Pages**
4. Set source to `main` branch, `/ (root)`
5. Your tool will be live at `https://yourusername.github.io/repo-name`

## 📋 Input CSV Expected Columns

```
Name, CountryCode, Phone, AllowBroadcast, AllowSMS, emailid, Amount, time, zoomads, zoomid, calendar
```

Only `Phone`, `emailid`, `zoomads`, and `zoomid` are used. All other columns are ignored.

## ✅ Output CSV Format

```
Phone, emailid, zoomads, zoomid
'+91-6289572538, user@gmail.com, https://zoom.us/webinar/register/WN_xxx, 96579230896
```

## 🛠 Tech

- Pure HTML + CSS + JavaScript
- Zero dependencies, zero server needed
- Works offline
- Handles large files (6000+ rows) with chunked processing and progress bar
