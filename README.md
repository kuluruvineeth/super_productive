<h1 align="center">Super Productive</h1>

<p align="center">
  A team workspace with tasks, mind maps, a calendar, group chat and a Pomodoro timer.<br/>
  Built end to end on stream — every feature below exists in this repo.
</p>

<p align="center">
  <a href="https://www.youtube.com/watch?v=L3wBtVmnFho"><img src="https://img.shields.io/badge/watch%20the%20full%20build-12h%2038m-FF0000?logo=youtube&logoColor=white" alt="Watch the build"></a>
  <img src="https://img.shields.io/badge/Next.js-App%20Router-000000?logo=nextdotjs&logoColor=white" alt="Next.js">
  <img src="https://img.shields.io/badge/Prisma-2D3748?logo=prisma&logoColor=white" alt="Prisma">
  <img src="https://img.shields.io/badge/Supabase-3FCF8E?logo=supabase&logoColor=white" alt="Supabase">
</p>

<p align="center">
  <a href="https://www.youtube.com/watch?v=L3wBtVmnFho">
    <img src="https://img.youtube.com/vi/L3wBtVmnFho/maxresdefault.jpg" width="720" alt="Build Your Ultimate Productivity App — the full 12-hour build">
  </a>
</p>

---

## What it does

**Workspaces.** Create a workspace, invite people by link, assign roles. Permissions are enforced
server-side through a `UserPermission` enum — owner, admin, can-edit, read-only — not hidden in the UI.

**Tasks.** A rich editor with tags, emoji, due-date ranges, assignees, and a starred view. Tasks can be
created from anywhere with a keyboard shortcut.

**Mind maps.** A node-and-edge canvas with unlimited nodes, tags, colours and per-node assignees.
Saved separately from tasks so a map can outlive the task that started it.

**Calendar.** Tasks and mind maps with date ranges appear on a shared month view.

**Group chat.** Per-workspace conversations with message history, edit and delete, and online presence.

**Pomodoro.** Per-user durations, rounds, and a choice of sound effects — stored per account, not per browser.

**Notifications.** In-app notifications for assignment, invitation and workspace changes, with seen/clicked
state tracked separately so a badge clears correctly across devices.

**Two languages.** English and Telugu, through `next-intl`.

## Stack

| | |
|---|---|
| Framework | Next.js App Router, TypeScript, React Server Components |
| Data | PostgreSQL via Prisma — 20 models including `Workspace`, `Task`, `MindMap`, `Tag`, `Notification`, `Conversation` |
| Auth | NextAuth with GitHub, Google, Apple, and credentials |
| Storage & realtime | Supabase |
| Client state | TanStack Query |
| UI | Tailwind CSS, Radix UI, next-themes |
| i18n | next-intl (`en`, `te`) |

Roughly 40 API route handlers under `app/api`, one concern each.

## Running it locally

```bash
git clone https://github.com/kuluruvineeth/super_productive.git
cd super_productive
npm install
cp env.example .env
```

Fill in `.env`:

```bash
DATABASE_URL=              # PostgreSQL connection string
NEXTAUTH_SECRET=           # openssl rand -base64 32
GITHUB_CLIENT_ID=          # optional, per provider you want
GITHUB_CLIENT_SECRET=
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
APPLE_CLIENT_ID=
APPLE_CLIENT_SECRET=
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=
```

Then:

```bash
npx prisma migrate dev
npm run dev
```

Open <http://localhost:3000>.

## Watch it being built

The complete build is one 12-hour session — no cuts, including the parts that broke.

**[▶ Build Your Ultimate Productivity App — full build (12h 38m)](https://www.youtube.com/watch?v=L3wBtVmnFho)**
· [Condensed version (33m)](https://www.youtube.com/watch?v=wfyjOLfavnU)
· [Full playlist, 44 parts](https://www.youtube.com/playlist?list=PLcAVdtHk_JSSWsnAm9Ucyp4wMI9Kg_706)

Feature walkthroughs:

| | |
|---|---|
| [Mind maps and collaboration](https://www.youtube.com/watch?v=iNX-qRZ17DQ) | [Workspace roles and online status](https://www.youtube.com/watch?v=pZ2_qUA1sbU) |
| [The advanced task editor](https://www.youtube.com/watch?v=2KWvJISjrZQ) | [Group chat](https://www.youtube.com/watch?v=CE3X1Ons3Js) |
| [Calendar view](https://www.youtube.com/watch?v=DP2d7bdebGo) | [Pomodoro timer](https://www.youtube.com/watch?v=1LZtNVQUtQE) |
| [Dynamic workspaces and localization](https://www.youtube.com/watch?v=wjJ_J5DMwj8) | [Starred tasks and maps](https://www.youtube.com/watch?v=ns3ZLpyBuSI) |

---

Built by [**@kuluruvineeth**](https://www.youtube.com/@kuluruvineeth) — I build AI products and take them apart on camera.
