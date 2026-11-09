<p align="center">
  <a href="https://github.com/forgeonsol/starforge"><img src="https://raw.githubusercontent.com/forgeonsol/starforge/main/.github/media/landing.png" alt="$FORGE · Starforge Arena. A browser arcade shooter with a live pilot leaderboard." /></a>
</p>

### hey, we're Starforge

We build **$FORGE**: a one-screen arcade shooter that runs in the browser, with a leaderboard that is honest about who is on it. Game, API, servers and deploy, end to end. We care how it **feels**, not just whether it works.

- **Arcade in the browser.** Three.js hangar, three hulls, a boss every forty seconds. Works on a phone, nothing to install, no wallet needed to play.
- **A board you can trust.** Every run is checked on the server: one-time run tickets, rate limits, plausibility checks, and a security log for everything rejected.
- **Sign-in without sign-up.** Your first finished run creates your pilot. HttpOnly session, hashed one-time recovery codes.
- **Self-hosted, boring in the good way.** Node 22 + SQLite with zero npm dependencies on the server, Docker + Caddy, automatic HTTPS, daily backups.

---

### Building: Starforge Arena

**$FORGE** is a Solana token that has not launched yet, with a real game behind it. Pick a hull, hold the forge against the swarm, break a boss every forty seconds and push your best run onto the shared board.

<p>
  <a href="https://github.com/forgeonsol/starforge"><img src="assets/btn-source.svg" alt="Source" /></a>
  <a href="https://github.com/forgeonsol/starforge#run-locally"><img src="assets/btn-run.svg" alt="Run locally" /></a>
  <a href="https://github.com/forgeonsol/starforge/blob/main/docs/security.md"><img src="assets/btn-security.svg" alt="Security" /></a>
</p>

#### How a run reaches the board

```mermaid
flowchart LR
  P["Play<br/>pick a hull, survive"] --> S["Submit<br/>POST /api/score"]
  S --> C{"Check<br/>ticket · rate limit · plausibility"}
  C -- "impossible" --> L[("security log")]
  C -- "verified" --> R["Rank<br/>best run per pilot"]
  R --> W["Watch<br/>board refreshes every 20 s"]
```

A run only counts if it started on the server at least as long ago as it lasted, and each ticket counts once. Rejected runs never touch the board.

<table>
  <tr>
    <td width="33%"><a href="https://github.com/forgeonsol/starforge"><img src="https://raw.githubusercontent.com/forgeonsol/starforge/main/.github/media/game.png" alt="Arena" /></a></td>
    <td width="33%"><a href="https://github.com/forgeonsol/starforge"><img src="https://raw.githubusercontent.com/forgeonsol/starforge/main/.github/media/leaderboard.png" alt="Leaderboard" /></a></td>
    <td width="33%"><a href="https://github.com/forgeonsol/starforge"><img src="https://raw.githubusercontent.com/forgeonsol/starforge/main/.github/media/hangar.png" alt="Hangar" /></a></td>
  </tr>
  <tr>
    <td><code>arena</code><br/>Swarm, shards, bosses.</td>
    <td><code>leaderboard</code><br/>Best verified run per pilot.</td>
    <td><code>hangar</code><br/>Spark, Anvil or Flux.</td>
  </tr>
</table>

**What's inside:** one-screen arena with timed bosses · pilot campaign and hangar · live leaderboard with daily movement · run tickets and plausibility checks · sign-in without registration · hardened Docker + Caddy stack · 59 end-to-end security checks in CI.

---

![Node.js](https://img.shields.io/badge/Node.js_22-161514?style=flat-square&logo=nodedotjs&logoColor=14F195)
![TypeScript](https://img.shields.io/badge/TypeScript-161514?style=flat-square&logo=typescript&logoColor=14F195)
![Three.js](https://img.shields.io/badge/Three.js-161514?style=flat-square&logo=threedotjs&logoColor=14F195)
![SQLite](https://img.shields.io/badge/SQLite-161514?style=flat-square&logo=sqlite&logoColor=14F195)
![Solana](https://img.shields.io/badge/Solana-161514?style=flat-square&logo=solana&logoColor=14F195)
![Docker](https://img.shields.io/badge/Docker-161514?style=flat-square&logo=docker&logoColor=14F195)
![Caddy](https://img.shields.io/badge/Caddy-161514?style=flat-square&logo=caddy&logoColor=14F195)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-161514?style=flat-square&logo=githubactions&logoColor=14F195)

<sub>$FORGE has not launched. It is a memecoin with no intrinsic value or expectation of financial return. Nothing here is financial advice.</sub>
