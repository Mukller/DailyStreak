# Руководство для контрибьютеров (DailyStreak)

Спасибо за интерес к проекту DailyStreak! Этот документ описывает процесс внесения вклада.

## 📋 Содержание

- [Кодекс поведения](#кодекс-поведения)
- [Как начать](#как-начать)
- [Стиль кода](#стиль-кода)
- [Типы вклада](#типы-вклада)
- [Pull Requests](#pull-requests)
- [Тестирование](#тестирование)

## 🤝 Кодекс поведения

Мы придерживаемся принципов вежливости и уважения:

- Будь вежлив и уважителен в общении
- Принимай конструктивную критику
- Сосредоточься на том, что лучше для сообщества
- Проявляй сочувствие к другим участникам

## 🚀 Как начать

### 1. Форкни репозиторий

Нажми **Fork** на странице репозитория.

### 2. Клонируй свой форк

```bash
git clone https://github.com/YOUR_USERNAME/DailyStreak.git
cd DailyStreak
```

### 3. Добавь upstream

```bash
git remote add upstream https://github.com/Mukller/DailyStreak.git
```

### 4. Создай ветку

```bash
git fetch upstream
git checkout -b feature/description upstream/main
```

**Правила именования веток:**
- `feature/name` — новые функции
- `bugfix/name` — исправление ошибок
- `improvement/name` — улучшения
- `docs/description` — документация

## 💻 Стиль кода

### Java код

```java
// ✅ ПРАВИЛЬНО
public class StreakManager {
    private final DailyStreakPlugin plugin;
    private final StreakStorage storage;

    public StreakManager(DailyStreakPlugin plugin, StreakStorage storage) {
        this.plugin = plugin;
        this.storage = storage;
    }

    /**
     * Получить текущую серию игрока.
     *
     * @param player игрок
     * @return количество дней серии
     */
    public int getPlayerStreak(Player player) {
        return storage.getStreak(player.getUniqueId());
    }

    public void incrementStreak(Player player) {
        if (player != null) {
            int newStreak = getPlayerStreak(player) + 1;
            storage.setStreak(player.getUniqueId(), newStreak);
        }
    }
}

// ❌ НЕПРАВИЛЬНО
public class StreakManager{
public DailyStreakPlugin p;
public StreakStorage s;
public StreakManager(DailyStreakPlugin p,StreakStorage s){this.p=p;this.s=s;}
public int getStreak(Player pl){return s.getStreak(pl.getUniqueId());}
```

### Требования

- Используй **camelCase** для переменных и методов
- Используй **PascalCase** для классов
- Максимум **100 символов** в строке
- Отступ — **4 пробела**
- Добавляй JavaDoc к публичным методам

### YAML конфигурация

```yaml
# ✅ ПРАВИЛЬНО
streak:
  enabled: true
  
  settings:
    timezone: "UTC+3"
    reset-time: "00:00"
    min-playtime: 10

rewards:
  7-day: 100
  30-day: 500
  365-day: 5000

# ❌ НЕПРАВИЛЬНО
streak: {enabled: true, tz: UTC+3}
rewards: [7: 100, 30: 500, 365: 5000]
```

## 📝 Типы вклада

### 1. Новые функции (Features)

```bash
git commit -m "feat: Add streak reset warning notification"
git commit -m "feat: Implement daily rewards system"
```

### 2. Исправление ошибок (Bugfixes)

```bash
git commit -m "fix: Correct timezone calculation for streak reset"
git commit -m "fix: Prevent negative streak values"
```

### 3. Улучшения (Improvements)

```bash
git commit -m "improvement: Optimize streak data loading"
git commit -m "improvement: Enhance leaderboard performance"
```

### 4. Документация (Docs)

```bash
git commit -m "docs: Update README with new commands"
git commit -m "docs: Add configuration examples"
```

## 🔄 Pull Requests

### Перед созданием PR

1. ✅ Код компилируется без ошибок
2. ✅ Функция протестирована на сервере
3. ✅ Обновлена документация (если нужно)
4. ✅ Обновлена конфигурация (если нужно)

### Описание PR

```markdown
## Описание
Краткое описание того, что делает этот PR.

## Тип изменения
- [ ] Новая функция
- [x] Исправление ошибки
- [ ] Улучшение производительности
- [ ] Обновление документации

## Как это тестировалось?
1. Запустил сервер на PaperMC X.X.X
2. Выполнил команду `/streak top`
3. Проверил логи на ошибки

## Связанные Issues
Closes #123

## Чек-лист
- [x] Код следует стилю проекта
- [x] Код протестирован
- [x] Документация обновлена
- [x] Нет breaking changes
```

## 🧪 Тестирование

### Что нужно тестировать

- ✅ Команды `/streak`, `/streak top`, `/streak <player>`
- ✅ Система сохранения данных
- ✅ Корректность сброса серии
- ✅ Выдача наград
- ✅ Конфигурация и её перезагрузка
- ✅ Совместимость с другими плагинами

### Локальное тестирование

```bash
# Компилируем
mvn clean package

# Копируем на тестовый сервер
cp target/DailyStreak-*.jar ~/test-server/plugins/

# Запускаем и тестируем функцию
```

## 🐛 Отчёты об ошибках

Если нашел баг, создай Issue с:

```
Версия плагина: X.X.X
Версия PaperMC: X.X.X
Java версия: 11/17/21

Описание проблемы:
[Подробное описание]

Шаги для воспроизведения:
1. ...
2. ...
3. ...

Ожидаемое поведение:
[Что должно было произойти]

Текущее поведение:
[Что произошло на самом деле]

Логи ошибок:
[Ошибки из консоли/логов]
```

## 💡 Типичные улучшения

### Идеи для PR

- 🎨 Улучшение визуального отображения "огонька"
- 📊 Более подробная статистика
- 🎁 Новые типы наград
- 🌍 Поддержка новых языков
- ⚡ Оптимизация производительности
- 🔐 Улучшение безопасности

### Перед работой над идеей

Создай Issue с идеей и жди обратной связи. Так мы избежим дублирования работы!

## 📖 Документация

При добавлении функции обновляй:

- **README.md** — описание команд
- **Inline комментарии** — в коде
- **config.yml** — новые параметры
- **CHANGELOG.md** — если существует

## ❓ Вопросы?

- Проверь существующие [Issues](https://github.com/Mukller/DailyStreak/issues)
- Создай новый Issue с пометкой `question`
- Смотри раздел [Support](README.md#-поддержка) в README

## 🎉 Спасибо!

Благодарим за вклад в развитие проекта! 🔥

---

**Happy Coding!** 💻
