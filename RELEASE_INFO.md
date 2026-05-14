# Описание для Release DailyStreak v1.0.0

**Используй это описание при создании релиза на GitHub**

---

## Release Title:
```
v1.0.0 - DailyStreak - Daily Streak System for PaperMC
```

## Release Description:
```markdown
## 🎉 Welcome to DailyStreak v1.0.0!

### ✨ Features in This Release

**Daily Streak System**
- 🔥 Real-time fire streak counter
- 📊 Automatic daily reset at configurable time
- 🎯 Player statistics tracking
- 💾 Persistent data storage (SQLite/MySQL)

**Leaderboard**
- 🏆 Top-10 players ranking
- 📈 Real-time updates
- 🎮 In-game leaderboard command

**Rewards System**
- 🎁 Configurable rewards for streaks
- 📍 7-day, 30-day, 365-day milestones
- 💰 Economy integration (Vault)
- 🔔 Reward notifications

**Admin Features**
- ⚙️ Complete configuration system
- 🔧 Per-command reload
- 👤 Player streak management
- 📊 Admin statistics

**Localization**
- 🇷🇺 Full Russian support
- 🇺🇸 English support
- 📝 Customizable messages

### 🛠️ Technical Details

**System Requirements:**
- Java 11 or higher
- PaperMC (Latest recommended)
- Minecraft 1.18+

**Dependencies:**
- Vault (optional, for economy integration)
- EssentialsEco or similar (optional)

**Database Support:**
- SQLite (default, no setup needed)
- MySQL/PostgreSQL (optional, for large servers)

### 📋 Commands

```
/streak                    # Show your streak
/streak <player>          # View other player's streak
/streak top               # View leaderboard
/streak help              # Show help

# Admin commands
/streak reset <player>    # Reset player streak
/streak set <player> <n>  # Set player streak
/streak reload            # Reload config
/streak stats <player>    # Full player stats
```

### 🔐 Permissions

```
dailystreak.use          # Basic command usage
dailystreak.view-others  # View other players' streaks
dailystreak.view-top     # View leaderboard
dailystreak.admin        # All admin commands
dailystreak.reload       # Reload configuration
dailystreak.reset        # Reset player streak
```

### ⚙️ Configuration

All settings are in `plugins/DailyStreak/config.yml`:

```yaml
settings:
  enabled: true
  timezone: "UTC+3"
  reset-time: "00:00"
  min-playtime: 10

rewards:
  7-day: 100
  30-day: 500
  365-day: 5000
```

### 📥 Installation

1. Download `DailyStreak.jar`
2. Place in `plugins/` folder
3. Restart server or `/reload`
4. Configure in `plugins/DailyStreak/config.yml`
5. Restart and enjoy!

### 🐛 Known Issues

None reported yet! Please report any issues.

### 🎮 Compatibility

| Version | Status |
|---------|--------|
| 1.20.x | ✅ Tested |
| 1.19.x | ✅ Tested |
| 1.18.x | ✅ Tested |

### 📖 Documentation

- [Full README](README.md)
- [Contributing Guide](CONTRIBUTING.md)
- [Code of Conduct](CODE_OF_CONDUCT.md)

### 🤝 Contributing

Want to help? Check out [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines!

### 📝 License

Licensed under MIT License - see [LICENSE](LICENSE)

### 🙏 Credits

Thanks to all the Minecraft community for inspiration and support!

---

**Happy Streaking! 🔥**
```

---

## Как использовать:

1. Открой https://github.com/Mukller/DailyStreak/releases
2. Нажми **"Create a new release"** или **"Draft a new release"**
3. Заполни форму:
   - **Tag version:** `v1.0.0`
   - **Release title:** `v1.0.0 - DailyStreak - Daily Streak System for PaperMC`
   - **Description:** Скопируй текст выше
4. Загрузи файл: `DailyStreak.jar`
5. Нажми **"Publish release"**

Готово! 🚀
