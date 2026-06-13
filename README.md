<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-purple?style=flat-square)](LICENSE.md)
[![maintained](https://img.shields.io/badge/maintained%3F-yes-green?style=flat-square)](https://github.com/Mukller/DailyStreak)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen?style=flat-square)](CONTRIBUTING.md)

---

## Language / Язык

</div>

| **📖 English** | **📖 Русский** |
|:---:|:---:|
| Scroll down / Листай вниз | Листай вниз / Scroll down |

---

## English Version




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

---

## Русская версия




# DailyStreak

<div align="center">

**🔥 Система ежедневных достижений "Огонек" как в TikTok для PaperMC**

[![License: MIT](https://img.shields.io/badge/License-MIT-purple?style=flat-square)](LICENSE.md)
[![Minecraft](https://img.shields.io/badge/Minecraft-1.16%2B-green?style=flat-square)](https://minecraft.net)
[![Java](https://img.shields.io/badge/Java-11%2B-blue?style=flat-square&logo=java)](https://www.java.com/)
[![PaperMC](https://img.shields.io/badge/PaperMC-Latest-orange?style=flat-square)](https://papermc.io)
[![maintained](https://img.shields.io/badge/maintained%3F-yes-green?style=flat-square)](https://github.com/Mukller/DailyStreak)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen?style=flat-square)](CONTRIBUTING.md)

[English](README_EN.md) • Русский

</div>

## 📌 Описание

DailyStreak — это инновационный плагин для PaperMC, который добавляет систему ежедневных достижений и "огонька" на твой сервер. Вдохновленный популярной функцией TikTok, этот плагин мотивирует игроков заходить на сервер каждый день и создает ощущение прогресса и достижений.

## ✨ Возможности

- 🔥 **Система "Огонька"** — отслеживание ежедневной активности
- 📊 **Таблица лидеров** — соревнование среди игроков
- 🎁 **Награды за серии** — поощрение верности игроков
- 💾 **Персистентные данные** — сохранение прогресса между сеансами
- ⚙️ **Полная конфигурация** — настрой под свой сервер
- 🌍 **Русская локализация** — полная поддержка русского языка
- 📈 **Статистика и аналитика** — отслеживание прогресса игроков
- 🎨 **Красивый интерфейс** — визуальное отображение "огонька"

## 🚀 Быстрый старт

### Требования

- **Java**: 11 или выше
- **PaperMC**: Latest версия рекомендуется
- **Права администратора** на сервере

### Установка

1. Скачай последнюю версию плагина (`.jar` файл)
2. Положи файл в папку `plugins/` твоего сервера
3. Перезагрузи сервер командой `/reload` или перезапусти его
4. Плагин готов к работе!

```bash
# Перезагрузка конфигурации
/reload
```

## 📖 Использование

### Основные команды

```
/streak                    # Показать свой огонек и статистику
/streak <ник>              # Показать огонек другого игрока
/streak top                # Топ-10 игроков по "огоньку"
/streak help               # Справка по командам
```

**Примеры:**
```
/streak                    # Показать мой огонек
/streak PlayerName         # Показать огонек игрока PlayerName
/streak top                # Показать лидеров сервера
```

### Автоматическое отслеживание

Плагин **автоматически** отслеживает:
- ✅ Вход игрока на сервер (каждый день)
- ✅ Время активности в игре
- ✅ Сохранение серии "огонька"
- ✅ Обнуление серии при пропуске дня

## ⚙️ Конфигурация

После первого запуска плагина в папке `plugins/DailyStreak/` будет создан файл `config.yml`.

### Пример config.yml

```yaml
# Основные настройки
settings:
  # Включить плагин
  enabled: true
  
  # Часовой пояс сервера (UTC, UTC+1, UTC+3 и т.д.)
  timezone: "UTC+3"
  
  # Время сброса "огонька" каждый день (часы:минуты)
  reset-time: "00:00"
  
  # Требуемое время онлайна для сохранения серии (в минутах)
  min-playtime: 10

# Награды за серии
rewards:
  # Награда за 7-дневную серию
  7-day: 100
  # Награда за 30-дневную серию
  30-day: 500
  # Награда за 365-дневную серию
  365-day: 5000

# Сообщения (кастомизация)
messages:
  prefix: "&8[&f⭐ DailyStreak&8]"
  
  # Поздравление при входе
  welcome: "&aДобро пожаловать! Твой огонек: &f{streak}🔥"
  
  # Сообщение при пропуске дня
  streak-lost: "&cТы потерял свой огонек! Начни заново с дня 1"
  
  # Сообщение при получении награды
  reward-earned: "&6🎁 Ты получил награду за &f{days}&6 дневную серию!"

# База данных
database:
  # Тип: SQLite, MySQL, PostgreSQL
  type: "SQLite"
  
  # MySQL/PostgreSQL (если используется)
  host: "localhost"
  port: 3306
  name: "minecraft"
  user: "root"
  password: "password"
```

Отредактируй файл под свои нужды и используй `/streak reload` для применения изменений.

## 🔐 Разрешения (Permissions)

```
dailystreak.use              # Базовое использование команды /streak
dailystreak.view-others      # Просмотр огонька других игроков
dailystreak.view-top         # Просмотр таблицы лидеров
dailystreak.admin            # Администраторские команды
dailystreak.reload           # Перезагрузить конфигурацию
dailystreak.reset            # Сбросить огонек игрока
```

### Пример с LuckPerms

```
/lp user <username> permission set dailystreak.use true
/lp user <username> permission set dailystreak.view-others true
/lp user <username> permission set dailystreak.view-top true
```

## 🎮 Как это работает?

### Система "Огонька"

1. **День 1** 🔥 — Игрок заходит в первый раз
2. **День 2** 🔥🔥 — Игрок заходит в следующий день
3. **День 3** 🔥🔥🔥 — И так далее...
4. **Пропуск дня** ❌ — Огонек обнуляется, начинаем с 1 🔥

### Награды

- **7 дней** подряд → Получи награду (стандартно 100 монет/очков)
- **30 дней** подряд → Большая награда (500 монет/очков)
- **365 дней** подряд → Легендарная награда (5000 монет/очков)

*Награды настраиваются в конфиге*

## 📊 Команды администратора

```
/streak reset <player>       # Сбросить огонек игрока
/streak set <player> <дни>   # Установить огонек игроку
/streak reload               # Перезагрузить конфиг
/streak stats <player>       # Показать полную статистику игрока
```

## 🐛 Частые проблемы

### Огонек не сохраняется

1. Проверь, что файлы сохраняются в папке `plugins/DailyStreak/`
2. Убедись, что база данных работает корректно
3. Проверь права доступа к папке плагина

### Команда /streak не работает

- Проверь разрешения (`dailystreak.use`)
- Убедись, что плагин включен в config.yml (`enabled: true`)
- Перезагрузи плагин: `/reload`

### Награды не выдаются

- Проверь, что установлены значения наград в config.yml
- Убедись, что система экономики установлена (Vault + EssentialsEco)
- Проверь логи плагина на ошибки

## 📊 Версионирование

Проект использует [Semantic Versioning](https://semver.org/):
- **MAJOR** — несовместимые изменения
- **MINOR** — новые функции, совместимые с предыдущими версиями
- **PATCH** — исправления ошибок

## 🤝 Вклад в проект

Мы приветствуем любые улучшения! Если хочешь помочь:

1. **Форк** репозитория
2. **Создай ветку** для твоей функции (`git checkout -b feature/AmazingFeature`)
3. **Закоммитай** изменения (`git commit -m 'Add some AmazingFeature'`)
4. **Запуши** ветку (`git push origin feature/AmazingFeature`)
5. **Открой Pull Request**

Подробнее см. [CONTRIBUTING.md](CONTRIBUTING.md)

## 📝 Лицензия

Проект распространяется под лицензией **MIT**. Подробнее см. файл [LICENSE](LICENSE).

**Ключевые моменты:**
- ✅ Можешь использовать в коммерческих целях
- ✅ Можешь модифицировать
- ✅ Можешь распространять
- ❌ Обязателен указание авторства и лицензии

## 👤 Автор

**Mukller**  
GitHub: [@Mukller](https://github.com/Mukller)

## 📮 Поддержка

Если у тебя возникли вопросы или ты нашел баг:

1. Проверь [Issues](https://github.com/Mukller/DailyStreak/issues) — может быть уже есть решение
2. Создай новую [Issue](https://github.com/Mukller/DailyStreak/issues/new) с подробным описанием
3. Укажи версию плагина и PaperMC

**При создании Issue укажи:**
```
Версия плагина: X.X.X
Версия PaperMC: X.X.X
Java версия: 11/17/21
Описание проблемы: ...
```

## 🎮 Совместимость

| Версия | Статус |
|--------|--------|
| 1.20+ | ✅ Полная поддержка |
| 1.19 | ✅ Поддерживается |
| 1.18 | ⚠️ Возможны проблемы |
| < 1.18 | ❌ Не поддерживается |

## 📚 Дополнительные ресурсы

- [PaperMC Документация](https://docs.papermc.io/)
- [Bukkit API](https://hub.spigotmc.org/javadocs/bukkit/)
- [SpigotMC (скачивание плагинов)](https://www.spigotmc.org/)
- [Vault (для экономики)](https://www.spigotmc.org/resources/vault.34315/)

## 🌟 Особенности

- ⚡ **Легкий и быстрый** — не нагружает сервер
- 🔐 **Безопасный** — защита от читерства и манипуляций
- 📱 **Мобильно-ориентированный** — вдохновлен современными трендами
- 🎯 **Геймификация** — мотивирует игроков возвращаться

---

<div align="center">

Made with ❤️ by Mukller

⭐ Если проект помог, поставь звезду!

</div>