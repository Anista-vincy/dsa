# Hospital Emergency Queue Visualizer (Python)

A Priority Queue visualizer built entirely in Python using standard libraries.

- **No external frameworks or packages required** (No Flask, Django, FastAPI, or Node.js).
- **No client-side JavaScript required**.
- **Ready for deployment on [Vercel](https://vercel.com/)** as a Serverless Python Function.

---

## Project Structure

```
├── api/
│   └── index.py         # Vercel Serverless Function entrypoint
├── app.py               # Main Python server & queue logic
├── style.css            # Stylesheet
├── vercel.json          # Vercel configuration & route rewrites
├── requirements.txt     # Python requirements (standard library only)
├── .gitignore           # Git ignore rules
├── .vercelignore        # Vercel build ignore rules
└── README.md            # Documentation
```

---

## How to Run Locally

1. Open your terminal or Command Prompt in this folder.
2. Run:
   ```bash
   python app.py
   ```
   *(or `py app.py` on Windows)*
3. Open your browser and navigate to:
   ```
   http://127.0.0.1:5000
   ```

---

## How to Host on Vercel

### Option 1: Deploy via GitHub (Recommended)

1. Push this folder to a GitHub repository:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin <your-github-repo-url>
   git push -u origin main
   ```
2. Go to [vercel.com](https://vercel.com/) and sign in.
3. Click **"Add New..."** > **"Project"**.
4. Import your GitHub repository.
5. Keep default settings (Framework Preset: **Other**) and click **"Deploy"**.
6. Vercel will build and assign you a live `.vercel.app` URL!

### Option 2: Deploy using Vercel CLI

1. Install the Vercel CLI globally (if you have Node.js):
   ```bash
   npm i -g vercel
   ```
2. In this folder, run:
   ```bash
   vercel
   ```
3. Follow the prompts to deploy. For production:
   ```bash
   vercel --prod
   ```

---

## Features

- **Priority Queue Implementation**: Automatically prioritizes critical emergency patients:
  - **Priority 1**: Critical
  - **Priority 2**: Serious
  - **Priority 3**: Moderate
  - **Priority 4**: Stable
- **FIFO within same priority**: Patients arriving earlier with equal severity are treated first.
- **Serverless Session Persistence**: Keeps patient queue state intact across requests using standard HTTP cookies.
- **Interactive Actions**:
  - Add Patient
  - Treat Next Patient
  - Load Demo Patients
  - Clear Queue
  - Queue Statistics tracking (Total Added, Treated, Waiting)
