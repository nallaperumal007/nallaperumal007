# ═══════════════════════════════════════════════════════
#   GitHub Profile README - Automation Workflows
#   For: Nalla Perumal's GitHub Profile
# ═══════════════════════════════════════════════════════
#
# SETUP INSTRUCTIONS:
# ══════════════════
# 1. Place each workflow in: .github/workflows/<filename>.yml
# 2. Push to your GitHub profile repo (same name as username)
# 3. Run workflows manually once via Actions tab to initialize
#
# ──────────────────────────────────────────────────────────────────────

# ╔══════════════════════════════════════════════════════════════════════╗
# ║  FILE: .github/workflows/snake.yml                                  ║
# ║  PURPOSE: Generates the contribution snake animation                ║
# ╚══════════════════════════════════════════════════════════════════════╝
#
# name: Generate Snake Animation
#
# on:
#   schedule:
#     - cron: "0 */12 * * *"   # Runs every 12 hours
#   workflow_dispatch:          # Manual trigger
#   push:
#     branches: [main]
#
# jobs:
#   generate:
#     permissions:
#       contents: write
#     runs-on: ubuntu-latest
#     timeout-minutes: 10
#
#     steps:
#       - name: Generate GitHub Snake (Dark)
#         uses: Platane/snk/svg-only@v3
#         with:
#           github_user_name: ${{ github.repository_owner }}
#           outputs: |
#             dist/github-snake.svg
#             dist/github-snake-dark.svg?palette=github-dark
#
#       - name: Push output to `output` branch
#         uses: crazy-max/ghaction-github-pages@v3.1.0
#         with:
#           target_branch: output
#           build_dir: dist
#         env:
#           GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

# ╔══════════════════════════════════════════════════════════════════════╗
# ║  FILE: .github/workflows/waka-readme.yml                            ║
# ║  PURPOSE: Updates WakaTime coding activity stats weekly             ║
# ╚══════════════════════════════════════════════════════════════════════╝
#
# PREREQUISITES:
#   - WakaTime account at https://wakatime.com
#   - Add WAKATIME_API_KEY to GitHub repo secrets
#
# name: WakaTime Stats
#
# on:
#   schedule:
#     - cron: "0 0 * * *"   # Every day at midnight UTC
#   workflow_dispatch:
#
# jobs:
#   update-readme:
#     name: Update WakaTime Stats
#     runs-on: ubuntu-latest
#     steps:
#       - uses: actions/checkout@v3
#       - name: WakaTime Readme Dev Metrics
#         uses: athul/waka-readme@master
#         with:
#           WAKATIME_API_KEY: ${{ secrets.WAKATIME_API_KEY }}

# ╔══════════════════════════════════════════════════════════════════════╗
# ║  FILE: .github/workflows/profile-readme.yml                         ║
# ║  PURPOSE: Refreshes pinned repos and profile metrics daily          ║
# ╚══════════════════════════════════════════════════════════════════════╝
#
# name: Update Profile README
#
# on:
#   schedule:
#     - cron: "0 6 * * *"   # Every day at 6 AM UTC
#   workflow_dispatch:
#   push:
#     branches: [main]
#
# jobs:
#   update-profile:
#     runs-on: ubuntu-latest
#     steps:
#       - uses: actions/checkout@v3
#
#       - name: Update README with latest repos
#         uses: marketplace/actions/latest-repos
#         with:
#           GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
#           USERNAME: nallaperumal
#           MAX_REPOS: 6

# ══════════════════════════════════════════════════════════════════════
#   QUICK SETUP CHECKLIST
# ══════════════════════════════════════════════════════════════════════
#
#  [ ] Create public repo named exactly: nallaperumal/nallaperumal
#  [ ] Copy README.md to root of that repo
#  [ ] Create .github/workflows/ directory
#  [ ] Add snake.yml workflow → auto-generates snake SVG
#  [ ] Add waka-readme.yml workflow → requires WakaTime API key
#  [ ] Go to GitHub Settings → Secrets → add WAKATIME_API_KEY
#  [ ] Replace all placeholder URLs with your real profiles:
#       - LinkedIn: linkedin.com/in/nallaperumal
#       - Twitter: twitter.com/nallaperumal
#       - Portfolio: nallaperumal.dev
#       - Email: nallaperumal@email.com
#  [ ] Update pinned repo names in README.md to match actual repos
#  [ ] Run workflows manually from Actions tab once to initialize
#  [ ] Enable "Read and write permissions" in Settings → Actions → General
#
# ══════════════════════════════════════════════════════════════════════
#   SERVICES USED (all free)
# ══════════════════════════════════════════════════════════════════════
#
#   github-readme-stats     → Stats cards, language charts, pinned repos
#   readme-typing-svg       → Animated typing header
#   capsule-render          → Hero & footer wave banners
#   skillicons.dev          → Tech stack icon grid
#   github-streak-stats     → Contribution streak counter
#   github-readme-activity  → Contribution activity graph
#   github-profile-trophy   → Achievement trophies
#   github-profile-summary  → Detailed profile cards
#   ghchart.rshah.org       → Contribution calendar heatmap
#   profile-counter.glitch  → Visitor counter
#   wakatime                → Real coding time tracking
#   Platane/snk             → Contribution snake animation
#   komarev.com/ghpvc       → Profile view counter badge
#
# ══════════════════════════════════════════════════════════════════════
