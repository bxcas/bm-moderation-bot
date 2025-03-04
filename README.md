## 📌 Overview
The **BattleMetrics Moderation Bot** is designed to allow trial staff to submit **mutes, kicks, bans, and lift bans** without requiring full access to **BattleMetrics** or other moderation tools. 

### How It Works:
- **Trial staff** submit moderation actions through Discord forms.  
- Actions remain **pending for approval** until reviewed by **verified staff**.  
- Verified staff can **accept, deny, or create a discussion thread** for further review.  
- The bot integrates exclusively with **BattleMetrics** and requires a **BattleMetrics RCON Subscription** to function.  

### Additional Features:
- **All bot actions are logged** in a dedicated `Logs` folder for full transparency and record-keeping.  
- Uses **BattleMetrics API** to ensure secure and efficient moderation.  



If you need assistance, contact **bxcas** on Discord.

---

# 🔧 Configuration Settings for BattleMetrics Moderation Bot

This section explains each configuration setting in the `config.json` file, what it does, and where to find the necessary values.

---

## 🛠 Discord Configuration (`discord`)

The `discord` section contains the bot's authentication details, server settings, and channels for admin messages.

```json
"discord": {
  "clientId": "BOT CLIENT ID",
  "token": "BOT TOKEN",
  "guildId": "DISCORD SERVER ID",
  "channels": {
    "message": "ADMINS CHANNEL ID",
    "request": "TRIAL CHANNEL REQUEST ID"
  },
  "roles": {
    "trialStaff": ["TRIAL STAFF ROLE ID 1", "TRIAL STAFF ROLE ID 2"],
    "seniorStaff": ["SENIOR STAFF ROLE ID 1", "SENIOR STAFF ROLE ID 2"]
  }
}
```
## 🔍 Where to Find These Values?

| Settings | Description | Where to Find It |
| :---         |     :---:      |          ---: |
| clientId   | The bot's unique ID.     |Discord Developer Portal → Select your bot → "OAuth2" tab.    |
| token     | The bot's authentication token.       |   Discord Developer Portal → Select your bot → "Bot" tab.      |
| guildId   | The ID of your Discord server.   | Right-click your server name in Discord → Click "Copy ID" |
| channels.message     | Admin notification channel ID.      | Right-click the channel in Discord → Click "Copy ID".     |
| channels.request   | Trial Lobby channel ID.     | Right-click the channel in Discord → Click "Copy ID".    |
| roles.trialStaff     | Role IDs for trial staff.       | Right-click the role in Discord → Click "Copy ID".       |
| roles.seniorStaff     |Role IDs for senior staff.	      | Right-click the role in Discord → Click "Copy ID".       |

---

## 🛡 BattleMetrics Configuration (battlemetrics)

This section contains settings related to `BattleMetrics`, which is used for managing bans and tracking players.

```json
"battlemetrics": {
  "organizationId": "BATTLEMETRICS ORGANIZATION ID",
  "banListId": "BATTLEMETRICS BAN LIST ID",
  "apiToken": "BATTLEMETRICS API TOKEN"
}
```
## 🔍 Where to Find These Values?

| Settings | Description | Where to Find It |
| :---         |     :---:      |          ---: |
| organizationId   | Your BattleMetrics Organization ID.    |Go to BattleMetrics Organization Page and find your organization ID.    |
| banListId     | The ID of your Ban List in BattleMetrics.       | Visit your ban list in BattleMetrics.     |
| apiToken   | The API token for BattleMetrics integration.   | Generate an API token on BattleMetrics |

---

🌐 Server Configuration (servers)

This section defines the `Rust servers` managed by the bot.

```json
"servers": [
  {
    "name": "SERVER NAME",
    "id": "SERVER ID"
  }
]

```
## 🔍 Where to Find These Values?

| Settings | Description | Where to Find It |
| :---         |     :---:      |          ---: |
| name   | The display name of the server.    |Choose a name that makes sense for you.   |
| id     | The server ID in BattleMetrics.     | Go to BattleMetrics Servers and find your server's ID in the URL. |


---

## 🔥 Example Full Configuration

```json
{
  "discord": {
    "clientId": "123456789012345678",
    "token": "YOUR_DISCORD_BOT_TOKEN",
    "guildId": "987654321098765432",
    "channels": {
      "message": "123456789012345678",
      "request": "876543210987654321"
    },
    "roles": {
      "trialStaff": ["123456789012345678", "234567890123456789"],
      "seniorStaff": ["345678901234567890", "456789012345678901"]
    }
  },
  "battlemetrics": {
    "organizationId": "112233",
    "banListId": "445566",
    "apiToken": "your_battlemetrics_api_token"
  },
  "servers": [
    {
      "name": "Main Rust Server",
      "id": "999999"
    },
    {
      "name": "Test Server",
      "id": "888888"
    }
  ]
}
```
