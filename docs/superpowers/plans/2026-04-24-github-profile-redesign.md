# GitHub Profile Redesign Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the cluttered GitHub profile README with a clean dark-mode design featuring a green name accent, circular photo, and a single activity graph widget.

**Architecture:** Three file operations — create an SVG header asset, rewrite README.md, delete the 3D workflow file. No dependencies between tasks 1 and 3; task 2 depends on task 1 completing first.

**Tech Stack:** Markdown, HTML (GitHub-flavored), SVG, shields.io badges, github-readme-activity-graph

---

## File Map

| File | Action | Purpose |
|---|---|---|
| `src/profile-header.svg` | Create | Renders `# joel` in green (#3fb950) monospace — used as `<img>` in README |
| `README.md` | Full rewrite | Profile page: header, projects, currently, activity graph |
| `.github/workflows/profile-3d.yml` | Delete | Removes daily cron that commits 3D SVGs back to the repo |

---

### Task 1: Create the green header SVG

**Files:**
- Create: `src/profile-header.svg`

- [ ] **Step 1: Create the SVG file**

Write `src/profile-header.svg` with this exact content:

```svg
<svg xmlns="http://www.w3.org/2000/svg" width="180" height="48">
  <text
    x="0"
    y="36"
    font-family="ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,monospace"
    font-size="32"
    font-weight="700"
    fill="#3fb950"
  ># joel</text>
</svg>
```

- [ ] **Step 2: Verify the SVG renders correctly**

Open `src/profile-header.svg` in a browser. You should see `# joel` in bold green monospace on a transparent background. The text should not be clipped.

- [ ] **Step 3: Commit**

```bash
git add src/profile-header.svg
git commit -m "feat: add green header SVG for profile README"
```

---

### Task 2: Rewrite README.md

**Files:**
- Modify: `README.md` (full rewrite)
- Depends on: Task 1 (SVG must exist for the img reference to be valid)

- [ ] **Step 1: Rewrite README.md with this exact content**

```markdown
<table>
  <tr>
    <td valign="middle" width="100">
      <img src="src/me.jpeg" width="80" style="border-radius:50%" alt="Joel" />
    </td>
    <td valign="middle">
      <img src="src/profile-header.svg" alt="# joel" height="42" /><br/>
      Data scientist. Builder. Interested in agentic architecture, automation, and personalization.<br/><br/>
      <a href="https://www.linkedin.com/in/joel-antony-xaviour-97394a140/">
        <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"/>
      </a>
      &nbsp;
      <a href="https://twitter.com/joeloffbeat">
        <img src="https://img.shields.io/badge/Twitter-1DA1F2?style=flat-square&logo=twitter&logoColor=white" alt="Twitter"/>
      </a>
      &nbsp;
      <a href="https://www.instagram.com/joeloffbeat/">
        <img src="https://img.shields.io/badge/Instagram-E4405F?style=flat-square&logo=instagram&logoColor=white" alt="Instagram"/>
      </a>
    </td>
  </tr>
</table>

---

### what I build

| Project | Description |
|---|---|
| [Joel's Mindscape](https://joeloffbeat.github.io) | 2D isometric web experience built with Three.js and Vite |
| [Holocorn](https://github.com/joeloffbeat/holocorn) | Tool for managing public relations |
| [Genesis](https://github.com/joeloffbeat/genesis) | Agent world sandbox |

---

### currently

> Building data pipelines, curating a personal design system, and pushing the edges of agentic architecture.

---

### github

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=joeloffbeat&hide_border=true&bg_color=0d1117&color=7d8590&line=3fb950&point=3fb950&area=true&area_color=3fb950&title_color=3fb950" alt="Joel's Activity Graph" />
</p>
```

- [ ] **Step 2: Preview the README locally**

Open `README.md` in VS Code's Markdown Preview (Ctrl+Shift+V) or push to a branch and check the GitHub preview. Verify:
- Circular photo appears left of the header text
- `# joel` SVG is visible and green
- Three badge links appear (LinkedIn, Twitter, Instagram)
- Projects table renders with links
- Activity graph URL is correct (no line breaks in the URL)

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: rewrite profile README with minimal dark design"
```

---

### Task 3: Delete the 3D contribution workflow

**Files:**
- Delete: `.github/workflows/profile-3d.yml`

- [ ] **Step 1: Delete the workflow file**

```bash
git rm .github/workflows/profile-3d.yml
```

If a `profile-3d-contrib/` directory exists in the repo, also run:

```bash
git rm -r profile-3d-contrib/
```

- [ ] **Step 2: Commit**

```bash
git commit -m "chore: remove 3D contribution graph workflow"
```

---

### Task 4: Final check and push

- [ ] **Step 1: Review the full diff**

```bash
git log --oneline -5
git diff HEAD~3 HEAD --stat
```

Expected output shows 3 commits: SVG creation, README rewrite, workflow deletion.

- [ ] **Step 2: Push to main**

```bash
git push origin main
```

- [ ] **Step 3: Verify on GitHub**

Open `https://github.com/joeloffbeat` in a browser. Confirm:
- Green `# joel` header renders (may take a minute for GitHub's CDN to update)
- Circular photo sits beside the header
- Projects table is clean with no badge walls
- Activity graph loads with dark background and green line
- No 3D SVG at the bottom
- No stats/streak/trophy widgets
