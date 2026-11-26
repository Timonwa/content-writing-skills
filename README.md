# content-writing-skills

Agent skills that help writers plan, write, edit and review blog posts, newsletters and social posts, on any subject, in any IDE or AI agent that supports [Agent Skills](https://agentskills.io).

[![License: MIT](https://img.shields.io/github/license/Timonwa/content-writing-skills)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-compatible-6E56CF)](https://agentskills.io)
[![GitHub stars](https://img.shields.io/github/stars/Timonwa/content-writing-skills?style=flat)](https://github.com/Timonwa/content-writing-skills/stargazers)
[![Buy Me a Coffee](https://img.shields.io/badge/Buy%20me%20a%20coffee-support-FFDD00?logo=buymeacoffee&logoColor=black)](https://buymeacoffee.com/timonwa)

## Contents

- [What's in it](#whats-in-it)
- [How the skills work](#how-the-skills-work)
- [Install](#install)
- [Set up a publication](#set-up-a-publication)
- [Skills](#skills)
- [Commands](#commands)
- [Contributing](#contributing)
- [Support](#support)

## What's in it

These skills are for anyone who writes blog posts, newsletters, social posts or guest posts, on any subject. They take a piece from the idea to how it performs: planning, research, interviews, drafting, images, editing, review, getting found, cross-posting, refreshing and pitching. They also hold the rules under every piece: plain language, sourced claims, code samples that run, and a check for machine-written prose.

For documentation — developer docs, help-centre articles, API references, READMEs, release notes — see [technical-writing-skills](https://github.com/Timonwa/technical-writing-skills).

## How the skills work

- Your agent picks a skill when your request matches it, so you don't have to name it. Commands run only when you call them.
- A skill reads your publication's guide first, then asks only what's still missing.
- Every file it writes — a brief, a post, a report — follows a fixed template, so each run looks the same.
- It never invents a fact, figure or quote. A gap stays marked until you fill it.

## Install

### Any IDE or AI agent

```shell
npx skills add Timonwa/content-writing-skills
```

[`npx skills`](https://github.com/vercel-labs/skills) asks which skills to install and which agents to install them for, and installs them in the current project. Add `-g` to install them for every project. To get the latest changes, run `npx skills update`.

Without Node, copy the folders inside `plugins/cw/skills/` into `.agents/skills/` in your project, or `~/.agents/skills/` for every project. Many agents read that folder. For the rest, use the skills folder your agent's docs name.

### Claude app (web or desktop)

Install the plugin once, then work in a Project for each publication (see [Set up a publication](#set-up-a-publication)).

1. Open **Customize > Plugins**.
2. Select **Add > Add marketplace > Add from a repository**, and enter `Timonwa/content-writing-skills`.
3. Add **cw**.
4. Turn on **Settings > Capabilities > Create and edit files**. Skills don't run without it. On Team and Enterprise plans, an admin turns it on.

Plugins are saved to your account, so they work in chat on mobile too. To get the latest changes, select **Check for updates** in **Customize > Plugins**, or turn on **Sync automatically** for the marketplace.

## Set up a publication

The skills write for a blog or newsletter using what you've recorded about it: who reads it, how it sounds, how it looks. Say "set up my publication" and `style-guide` builds those files with you. Leave anything you haven't decided blank, and a skill asks about it later.

```text
publications/
├── <publication>/
│   ├── profile.md              # who it's for and what it's for
│   ├── writing-guide.md        # how it sounds
│   ├── brand.md                # how it looks
│   ├── media-kit.md            # the audience facts a sponsor email cites
│   ├── sources/                # style guides you already have
│   ├── examples/               # sample covers, logos and typical pieces
│   ├── calendar.md             # one line per topic: date, formats, status, who's on it
│   ├── series/                 # one folder per series: its brief and what its parts share
│   ├── reports/                # performance reviews
│   └── topics/
│       └── <yyyy-mm>-<slug>/   # one folder per topic, e.g. 2026-12-sourdough-starter
│           ├── brief.md        # what the topic becomes, its status and who holds it
│           ├── blog.md         # the blog post
│           ├── newsletter.md   # the newsletter issue
│           ├── social.md       # the social posts
│           ├── copies.md       # copies on other blogging platforms
│           ├── sources.md      # the source log
│           ├── interviews/     # interview notes
│           ├── images/         # cover, share card and diagrams
│           └── reports/        # review, AI-writing check and SEO check
└── pitch-log.md                # every pitch and proposal, sent and received
```

**In a codebase:**

- Name the folder in the project's `AGENTS.md`, which every coding agent reads: `Publications: publications/`.
- For a folder outside the repo, add the same line to your agent's personal instructions file.
- If nothing names a folder, the skills look for `publications/`, then ask.

**In a chat app:**

- Make one project per publication. Add its files, your logo, sample covers and any style guide you already have.
- Chat-app projects can't hold folders, so a topic's files are named `<topic folder>--<file>`, such as `2026-12-sourdough-starter--blog.md`.
- When the agent gives you an updated file, replace the old one. For `calendar.md`, it gives you only the line to change.
- Outside a project, attach the files to the chat.

## Skills

| Skill                  | Use it to                                                                                                                                         |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `writing-standards`    | Check that a piece is clear, plain and backed by sources                                                                                          |
| `code-samples`         | Add code to a tutorial or post that readers can copy and run                                                                                      |
| `content-planning`     | Decide what to write next, and plan a publishing calendar you can keep up with                                                                    |
| `content-research`     | Find reliable sources for a piece and check every fact and figure                                                                                 |
| `interviews`           | Interview anyone for a piece — an expert, a customer, a founder, someone with a story — and turn it into quotes, a Q&A, a profile or a case study |
| `article-standards`    | Write a blog post or article                                                                                                                      |
| `newsletter-standards` | Write a newsletter issue, including its subject line                                                                                              |
| `demo-project`         | Build the code project that goes with a coding tutorial                                                                                           |
| `images-and-diagrams`  | Choose photos, charts and diagrams, with the right credits and image descriptions                                                                 |
| `cover-images`         | Make a post's cover image, which also shows when the link is shared                                                                               |
| `editing-standards`    | Edit a post or newsletter issue, keeping the writer's own voice                                                                                   |
| `seo-aeo-geo`          | Help readers find your post through Google and AI tools like ChatGPT                                                                              |
| `social-media-posts`   | Write social posts to promote a piece or share news, for any platform                                                                             |
| `cross-posting`        | Republish a post on Medium, Substack, dev.to or similar, without hurting the original's ranking                                                   |
| `content-refresh`      | Update, correct, merge or remove old posts                                                                                                        |
| `pitching`             | Write pitch emails, guest post and collaboration proposals, sponsor emails and replies                                                            |
| `style-guide`          | Set up your blog or newsletter's profile, writing guide, look and media kit                                                                       |

## Commands

| Command               | Use it to                                                                        |
| --------------------- | -------------------------------------------------------------------------------- |
| `content-review`      | Check a post or newsletter issue is ready to publish                             |
| `ai-check`            | Find what makes a piece sound machine-written, with a suggested rewrite for each |
| `content-performance` | See which posts to fix first, from your analytics export                         |

- A command reports what it finds and doesn't edit anything while it checks.
- Every command except `content-performance` takes `--fix`, which fixes only the findings you choose.
- Reports go to the topic's or publication's `reports/`.
- Nothing is ever posted, published or scheduled for you.

## Contributing

Issues and pull requests are welcome, especially for a rule that misfires on your writing or has fallen behind the standard it cites. In a pull request:

- Change one skill where you can.
- Update its `evals/evals.json`.
- Keep `SKILL.md` under 200 lines and its description under 550 characters, and give a new skill a name no other skill uses. Longer material goes in the skill's `references/` folder, which the agent reads only when it needs it.
- Run the checks:

| Script              | Use it to                                                                                                                                     | Needs                       |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------- |
| `pnpm format`       | Format everything with Prettier                                                                                                               | `pnpm install` first        |
| `pnpm format:check` | Check formatting without writing                                                                                                              | `pnpm install` first        |
| `pnpm check:skills` | Check every skill against the Agent Skills rules and the house limits: 200 lines, a 550-character description, and a name no other skill uses | Node                        |
| `pnpm validate`     | Validate the Claude Code marketplace and plugin manifests                                                                                     | the Claude Code CLI on PATH |

The skills are Markdown, so there's no build step, and Prettier is the only dependency. Without installing it, run `pnpm dlx prettier --write .` instead.

## Support

If these skills save you time, [star the repo](https://github.com/Timonwa/content-writing-skills) so other writers can find it, or [buy me a coffee](https://buymeacoffee.com/timonwa).

For documentation, see [technical-writing-skills](https://github.com/Timonwa/technical-writing-skills). For web apps built with Next.js, React and Firebase, see [engineering-skills](https://github.com/Timonwa/engineering-skills).

## License

[MIT](LICENSE)
