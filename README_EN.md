# DailyStreak

<div align="center">

**🔥 Daily Streak System - TikTok-style Fire System for PaperMC**

[![Java](https://img.shields.io/badge/Java-11%2B-blue?style=flat-square&logo=java)](https://www.java.com/)
[![PaperMC](https://img.shields.io/badge/PaperMC-Latest-green?style=flat-square&logo=minecraft)](https://papermc.io)
[![License](https://img.shields.io/badge/License-MIT-purple?style=flat-square)](LICENSE)

[English](README_EN.md) • [Русский](README.md)

</div>

## 📌 Description

DailyStreak is an innovative PaperMC plugin that adds a daily achievement and "fire streak" system to your server. Inspired by the popular TikTok feature, this plugin motivates players to log in every day and creates a sense of progress and accomplishment.

## ✨ Features

- 🔥 **Streak System** — track daily activity with visual fire emojis
- 📊 **Leaderboard** — competitive ranking among players
- 🎁 **Streak Rewards** — reward player loyalty and consistency
- 💾 **Persistent Data** — progress saved between sessions
- ⚙️ **Full Customization** — adapt to your server needs
- 🌍 **Multi-language Support** — Russian and English included
- 📈 **Statistics & Analytics** — track player progress
- 🎨 **Beautiful Interface** — visual streak display

## 🚀 Quick Start

### Requirements

- **Java**: 11 or higher
- **PaperMC**: Latest version recommended
- **Server administrator** privileges

### Installation

1. Download the latest version of the plugin (`.jar` file)
2. Place the file in the `plugins/` folder of your server
3. Reload the server with `/reload` or restart it completely
4. Plugin is ready to use!

```bash
# Reload configuration
/reload
```

## 📖 Usage

### Main Commands

```
/streak                    # Show your fire streak and stats
/streak <player_name>      # Show another player's streak
/streak top                # Top-10 players by streak
/streak help               # Command help
```

**Examples:**
```
/streak                    # Show my streak
/streak PlayerName         # Show PlayerName's streak
/streak top                # Show server leaderboard
```

### Automatic Tracking

The plugin **automatically** tracks:
- ✅ Player login (every day)
- ✅ Active gameplay time
- ✅ Streak preservation
- ✅ Streak reset on missed day

## ⚙️ Configuration

After the first plugin run, a `config.yml` file will be created in the `plugins/DailyStreak/` folder.

### Example config.yml

```yaml
# Main settings
settings:
  # Enable plugin
  enabled: true
  
  # Server timezone (UTC, UTC+1, UTC+3, etc.)
  timezone: "UTC+3"
  
  # Streak reset time every day (hours:minutes)
  reset-time: "00:00"
  
  # Required playtime to keep streak (in minutes)
  min-playtime: 10

# Streak rewards
rewards:
  # 7-day streak reward
  7-day: 100
  # 30-day streak reward
  30-day: 500
  # 365-day streak reward
  365-day: 5000

# Messages (customization)
messages:
  prefix: "&8[&f⭐ DailyStreak&8]"
  
  # Welcome message on login
  welcome: "&aWelcome! Your streak: &f{streak}🔥"
  
  # Message when streak is lost
  streak-lost: "&cYou lost your streak! Start fresh with day 1"
  
  # Reward notification
  reward-earned: "&6🎁 You earned a reward for &f{days}&6-day streak!"

# Database
database:
  # Type: SQLite, MySQL, PostgreSQL
  type: "SQLite"
  
  # MySQL/PostgreSQL (if used)
  host: "localhost"
  port: 3306
  name: "minecraft"
  user: "root"
  password: "password"
```

Edit the file according to your needs and use `/streak reload` to apply changes.

## 🔐 Permissions

```
dailystreak.use              # Basic command usage
dailystreak.view-others      # View other players' streaks
dailystreak.view-top         # View leaderboard
dailystreak.admin            # Admin commands
dailystreak.reload           # Reload configuration
dailystreak.reset            # Reset player streak
```

### Example with LuckPerms

```
/lp user <username> permission set dailystreak.use true
/lp user <username> permission set dailystreak.view-others true
/lp user <username> permission set dailystreak.view-top true
```

## 🎮 How It Works?

### Streak System

1. **Day 1** 🔥 — Player's first login
2. **Day 2** 🔥🔥 — Player logs in next day
3. **Day 3** 🔥🔥🔥 — And so on...
4. **Missed Day** ❌ — Streak resets to 1 🔥

### Rewards

- **7 days** in a row → Get a reward (default 100 coins/points)
- **30 days** in a row → Big reward (500 coins/points)
- **365 days** in a row → Legendary reward (5000 coins/points)

*Rewards are customizable in config*

## 📊 Admin Commands

```
/streak reset <player>       # Reset player's streak
/streak set <player> <days>  # Set streak for player
/streak reload               # Reload configuration
/streak stats <player>       # Show player's full statistics
```

## 🐛 Troubleshooting

### Streak not saving

1. Check that files are saved in `plugins/DailyStreak/` folder
2. Make sure database is working correctly
3. Check folder permissions

### /streak command doesn't work

- Check permissions (`dailystreak.use`)
- Make sure plugin is enabled in config.yml (`enabled: true`)
- Reload plugin: `/reload`

### Rewards not given

- Check reward values in config.yml
- Make sure economy system is installed (Vault + EssentialsEco)
- Check plugin logs for errors

## 📊 Versioning

The project uses [Semantic Versioning](https://semver.org/):
- **MAJOR** — incompatible changes
- **MINOR** — new features, backward compatible
- **PATCH** — bug fixes

## 🤝 Contributing

We welcome any improvements! If you want to help:

1. **Fork** the repository
2. **Create a branch** for your feature (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** your branch (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## 📝 License

The project is distributed under the **MIT** license. See [LICENSE](LICENSE) file for details.

**Key points:**
- ✅ Can be used for commercial purposes
- ✅ Can be modified
- ✅ Can be distributed
- ❌ Attribution and license must be included

## 👤 Author

**Mukller**  
GitHub: [@Mukller](https://github.com/Mukller)

## 📮 Support

If you have questions or found a bug:

1. Check [Issues](https://github.com/Mukller/DailyStreak/issues) — there might be a solution
2. Create a new [Issue](https://github.com/Mukller/DailyStreak/issues/new) with details
3. Specify plugin and PaperMC versions

**When creating an Issue, provide:**
```
Plugin version: X.X.X
PaperMC version: X.X.X
Java version: 11/17/21
Problem description: ...
```

## 🎮 Compatibility

| Version | Status |
|---------|--------|
| 1.20+ | ✅ Full support |
| 1.19 | ✅ Supported |
| 1.18 | ⚠️ Possible issues |
| < 1.18 | ❌ Not supported |

## 📚 Additional Resources

- [PaperMC Documentation](https://docs.papermc.io/)
- [Bukkit API](https://hub.spigotmc.org/javadocs/bukkit/)
- [SpigotMC (download plugins)](https://www.spigotmc.org/)
- [Vault (for economy)](https://www.spigotmc.org/resources/vault.34315/)

## 🌟 Highlights

- ⚡ **Lightweight and Fast** — doesn't burden your server
- 🔐 **Secure** — protection against cheating and manipulation
- 📱 **Modern Design** — inspired by trending social media
- 🎯 **Gamification** — motivates players to return

---

<div align="center">

Made with ❤️ by Mukller

⭐ If the project helped, star it!

</div>
