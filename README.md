# Mesh Chess

The whole `#chess` channel plays **White together** against a bot, over MeshCore radio. Vote the next move; the most
popular one is played; the bot answers. Win and it levels up.

**Live board:** https://meshscore-chess.harve6.workers.dev/

Powered by MeshScore. The board now runs on Cloudflare; this repo only holds the README and a redirect for the old address.

## How to play

1. Join the **#chess** channel in the MeshCore app (scan the QR on the board, or add a hashtag channel named `chess`).
2. Send `!move e4` (or any legal move).
3. The first vote of a round starts a **5 minute clock**. Everyone's votes count; the most votes wins (ties go to the
   earliest vote).
4. The bot replies with one post per round. Checkmate it to level up.

## Commands

Send them on `#chess` (or by DM as `!chess <command>`).

| Command | What it does |
|---|---|
| `!move e4` | Vote a move. Also `Nf3`, `O-O`, `e2e4`, `nf3`, `0-0`. `!m` is short. Vote again to change your mind |
| `!board` | Game number, level, last moves, vote counts, time left |
| `!moves` | List the legal moves |
| `!top` | The crowd's record and the top move-pickers |
| `!puzzle` | Show today's puzzle |
| `!puzzle Qh5` | Answer the puzzle (3 tries; multi-move puzzles reply with the opponent's move) |
| `!answer` | Show the puzzle's solution |
| `!mode max\|min\|off` | Admin: `min` posts results and the puzzle only |
| `!newgame [1-8]` | Admin: start a fresh game, optionally at a level |
| `!help`, `!ping`, `!botstatus` | Help, a radio check, bot health |

## Features

- **Crowd vs bot:** one shared game, everyone votes, one channel post per round.
- **8 levels:** Beginner, Novice, Casual, Club, Strong, Expert, Master, Grandmaster. Beat a level to climb; a loss or
  draw replays the same level.
- **Daily puzzle:** a new [Lichess](https://lichess.org) puzzle every morning.
- **Live web board:** position with the last move, vote bars and countdown, move list, level ladder, top
  contributors, past games and the puzzle.
- **Easy to join:** scannable channel QR on the board, plus an optional contact QR so the bot can DM your vote
  confirmations.
- **Light on airtime:** an empty channel costs nothing, restarts post nothing, and vote acks go by DM.

## For the operator

The bot uploads the page and `state.json` to a Cloudflare Worker (`site_api` in the bot's `[bots.chess]` settings).
