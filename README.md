<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-purple?style=flat-square)](LICENSE.md)
[![maintained](https://img.shields.io/badge/maintained%3F-yes-green?style=flat-square)](https://github.com/Mukller/DailyStreak)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen?style=flat-square)](CONTRIBUTING.md)

### 🌐 Язык / Language

**Нажми, чтобы развернуть нужный язык · Click to expand your language**

</div>

<details open>
<summary><b>🇬🇧 English</b></summary>

<br>

# DailyStreak

<div align="center">

**🔥 A daily-achievement "streak" system like TikTok's, for PaperMC**

[![Java](https://img.shields.io/badge/Java-11%2B-blue?style=flat-square&logo=java)](https://www.java.com/)
[![PaperMC](https://img.shields.io/badge/PaperMC-Latest-green?style=flat-square&logo=minecraft)](https://papermc.io)
[![License](https://img.shields.io/badge/License-MIT-purple?style=flat-square)](LICENSE)

</div>

## 📌 Description

DailyStreak is an innovative PaperMC plugin that adds a daily-achievement and "streak" system to your server. Inspired by the popular TikTok feature, it motivates players to log in every day and creates a sense of progress and achievement.

## ✨ Features

- 🔥 **Streak system** — tracks daily activity
- 📊 **Leaderboard** — competition among players
- 🎁 **Streak rewards** — encourages player loyalty
- 💾 **Persistent data** — progress is saved between sessions
- ⚙️ **Full configuration** — tune it for your server
- 🌍 **Russian localization** — full Russian language support
- 📈 **Statistics and analytics** — track player progress
- 🎨 **Nice UI** — visual display of the streak

## 🚀 Quick start

### Requirements

- **Java**: 11 or higher
- **PaperMC**: latest version recommended
- **Admin rights** on the server

### Installation

1. Download the latest plugin version (`.jar` file)
2. Place the file into your server's `plugins/` folder
3. Reload the server with `/reload` or restart it
4. The plugin is ready to go!

```bash
# Reload the configuration
/reload
```

## 📖 Usage

### Main commands

```
/streak                    # Show your streak and stats
/streak <name>             # Show another player's streak
/streak top                # Top 10 players by streak
/streak help               # Command help
```

**Examples:**
```
/streak                    # Show my streak
/streak PlayerName         # Show PlayerName's streak
/streak top                # Show the server leaders
```

### Automatic tracking

The plugin **automatically** tracks:
- ✅ A player logging in (each day)
- ✅ Active in-game time
- ✅ Keeping the streak going
- ✅ Resetting the streak when a day is missed

## ⚙️ Configuration

On first launch the plugin creates `config.yml` in `plugins/DailyStreak/`.

### Example config.yml

```yaml
# Main settings
settings:
  # Enable the plugin
  enabled: true
  
  # Server timezone (UTC, UTC+1, UTC+3, etc.)
  timezone: "UTC+3"
  
  # Daily streak reset time (hours:minutes)
  reset-time: "00:00"
  
  # Required online time to keep the streak (in minutes)
  min-playtime: 10

# Streak rewards
rewards:
  # Reward for a 7-day streak
  7-day: 100
  # Reward for a 30-day streak
  30-day: 500
  # Reward for a 365-day streak
  365-day: 5000

# Messages (customization)
messages:
  prefix: "&8[&f⭐ DailyStreak&8]"
  
  # Welcome on login
  welcome: "&aWelcome! Your streak: &f{streak}🔥"
  
  # Message when a day is missed
  streak-lost: "&cYou lost your streak! Start again from day 1"
  
  # Message when a reward is earned
  reward-earned: "&6🎁 You earned a reward for a &f{days}&6-day streak!"

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

Edit the file to suit your needs and use `/streak reload` to apply changes.

## 🔐 Permissions

```
dailystreak.use              # Basic use of the /streak command
dailystreak.view-others      # View other players' streaks
dailystreak.view-top         # View the leaderboard
dailystreak.admin            # Admin commands
dailystreak.reload           # Reload the configuration
dailystreak.reset            # Reset a player's streak
```

### Example with LuckPerms

```
/lp user <username> permission set dailystreak.use true
/lp user <username> permission set dailystreak.view-others true
/lp user <username> permission set dailystreak.view-top true
```

## 🎮 How does it work?

### Streak system

1. **Day 1** 🔥 — the player logs in for the first time
2. **Day 2** 🔥🔥 — the player logs in the next day
3. **Day 3** 🔥🔥🔥 — and so on...
4. **A missed day** ❌ — the streak resets, starting from 1 🔥

### Rewards

- **7 days** in a row → get a reward (100 coins/points by default)
- **30 days** in a row → a big reward (500 coins/points)
- **365 days** in a row → a legendary reward (5000 coins/points)

*Rewards are configurable in the config*

## 📊 Admin commands

```
/streak reset <player>       # Reset a player's streak
/streak set <player> <days>  # Set a player's streak
/streak reload               # Reload the config
/streak stats <player>       # Show a player's full stats
```

## 🐛 Common issues

### The streak isn't saved

1. Check that files are saved in `plugins/DailyStreak/`
2. Make sure the database works correctly
3. Check the permissions on the plugin folder

### The /streak command doesn't work

- Check the permissions (`dailystreak.use`)
- Make sure the plugin is enabled in config.yml (`enabled: true`)
- Reload the plugin: `/reload`

### Rewards aren't granted

- Check that reward values are set in config.yml
- Make sure an economy system is installed (Vault + EssentialsEco)
- Check the plugin logs for errors

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
4. **Push** the branch (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## 📝 License

This project is distributed under the **MIT** license. See the [LICENSE](LICENSE) file for details.

**Key points:**
- ✅ You can use it commercially
- ✅ You can modify it
- ✅ You can distribute it
- ❌ Attribution and the license notice are required

## 👤 Author

**Mukller**  
GitHub: [@Mukller](https://github.com/Mukller)

## 📮 Support

If you have questions or found a bug:

1. Check [Issues](https://github.com/Mukller/DailyStreak/issues) — there may already be a solution
2. Create a new [Issue](https://github.com/Mukller/DailyStreak/issues/new) with a detailed description
3. Include the plugin and PaperMC version

**When creating an Issue, include:**
```
Plugin version: X.X.X
PaperMC version: X.X.X
Java version: 11/17/21
Problem description: ...
```

## 🎮 Compatibility

| Version | Status |
|--------|--------|
| 1.20+ | ✅ Full support |
| 1.19 | ✅ Supported |
| 1.18 | ⚠️ Possible issues |
| < 1.18 | ❌ Not supported |

## 📚 Extra resources

- [PaperMC Docs](https://docs.papermc.io/)
- [Bukkit API](https://hub.spigotmc.org/javadocs/bukkit/)
- [SpigotMC (plugin downloads)](https://www.spigotmc.org/)
- [Vault (for economy)](https://www.spigotmc.org/resources/vault.34315/)

## 🌟 Highlights

- ⚡ **Light and fast** — doesn't strain the server
- 🔐 **Secure** — protection against cheating and manipulation
- 📱 **Mobile-minded** — inspired by modern trends
- 🎯 **Gamification** — motivates players to return

---

<div align="center">

Made with ❤️ by Mukller

⭐ If the project helped, give it a star!

</div>

</details>

<details>
<summary><b>🇷🇺 Русский</b></summary>

<br>

# DailyStreak

<div align="center">

**🔥 Система ежедневных достижений "Огонек" как в TikTok для PaperMC**

[![Java](https://img.shields.io/badge/Java-11%2B-blue?style=flat-square&logo=java)](https://www.java.com/)
[![PaperMC](https://img.shields.io/badge/PaperMC-Latest-green?style=flat-square&logo=minecraft)](https://papermc.io)
[![License](https://img.shields.io/badge/License-MIT-purple?style=flat-square)](LICENSE)


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

</details>
