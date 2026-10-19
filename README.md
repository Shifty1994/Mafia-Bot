<div align="center">

# Mafia Bot – Group Edition

**Turn any group activity into a chaotic betrayal game**

[![Discord.js](https://img.shields.io/badge/discord.js-v14-blue?logo=discord)](https://discord.js.org/)
[![Node.js](https://img.shields.io/badge/Node.js-≥20-brightgreen?logo=node.js)](https://nodejs.org/)
[![License: ISC](https://img.shields.io/badge/License-ISC-yellow.svg)](LICENSE)

</div>

**Have your groups become too predictable and stale?**  
**Time to add Mafia drama, suspicion, gold incentives and maximum chaos.**

This Discord bot transforms World of Warcraft raids, dungeons, and other group activities into a social deduction game where some players are secretly Mafia trying to die ~3 times, one chaotic Jester wants to get voted, and everyone else tries to figure it out.

**Bonus mode** also works perfectly in Rocket League parties/custom games.

### How to Play (Classic Mode)

1. Everyone joins the **same Discord voice channel**
2. Group leader types  
   `/playmafia`  
    (or `/playmafia gamemode:classic force:true` if testing with few people)
3. Bot secretly assigns roles via DM:
   - **~20% Mafia** — know each other, goal = **die 3+ times** (excl. big wipes)
   - **~10% Jester** — goal = act suspicious so people vote you at the end
   - Rest = **Town** — identify the impostors
4. Play the activity normally
5. After the run → vote in text chat (each player names suspects)
6. Gold is split based on votes + death count

20% are mafia, 10% jester, 70% town

| Players | Mafia | Jester | Town |
| ------- | ----- | ------ | ---- |
| 1       | 1     | 0      | 0    |
| 3       | 1     | 0      | 2    |
| 5       | 1     | 0      | 4    |
| 10      | 2     | 1      | 7    |
| 20      | 4     | 2      | 14   |

### Win Conditions & Gold Split

Gold is divided evenly among **all winners**:

- **Jester** → gets majority votes → share gold (included in split)
- **Mafia** → died 3+ times **and** no majority votes against them → share gold
- **Town** → voted at least one real Mafia into majority → share gold

### Commands

| Command                       | Description                                      |
|-------------------------------|--------------------------------------------------|
| `/playmafia`                  | Classic mode (auto-scales roles)                 |
| `/playmafia gamemode:classic` | Explicit Classic mode                            |
| `/playmafia gamemode:sabotage`| Objective-based Sabotage mode                    |
| `/playmafia gamemode:simple`  | Simple mode (1 secret Mafia)                     |
| `/playmafia force:true`       | Force start even with < 2 players (testing)      |

### Features

- Dynamic role scaling based on player count
- Private DMs for role & team info
- Beautiful public rules embed
- Silent handling of closed DMs
- Works in any voice channel

### Self-Hosting

1. Clone the repo
   ```bash
   git clone https://github.com/Shifty1994/Mafia-Bot
   cd mafia-bot

2. Install dependencies
    npm install

3. Create .env from .env.example and fill in:
    TOKEN=your-bot-token-here
    CLIENT_ID=your-application-id-here

4. Deploy slash commands (run once, or after changes)
    node deploy-commands.js

5. Start the bot
    npm run start 