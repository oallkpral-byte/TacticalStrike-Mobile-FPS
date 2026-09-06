# 🚀 TacticalStrike Mobile - Quick Start Guide

## Быстрый запуск проекта

### Требования
- **Unity 6 LTS** (или Unity 2022 LTS)
- **C# 9.0+**
- **Android SDK** (для Android-версии) или **Xcode** (для iOS)
- **Photon Fusion** (будет установлен через Package Manager)
- **Visual Studio / VS Code** (для редактирования C# кода)

---

## 📥 Шаг 1: Клонирование репозитория

```bash
git clone https://github.com/oallkpral-byte/TacticalStrike-Mobile-FPS.git
cd TacticalStrike-Mobile-FPS
```

---

## 🎮 Шаг 2: Открытие проекта в Unity

1. Откройте **Unity Hub**
2. Нажмите **"Add project"** → выберите папку `TacticalStrike-Mobile-FPS`
3. Убедитесь, что установлена **Unity 6 LTS**
4. Нажмите **"Open"**

> ⚠️ Первый запуск может занять 5–10 минут (импорт ассетов и компиляция)

---

## 📦 Шаг 3: Установка зависимостей

После открытия проекта:

### 3.1 Photon Fusion
```
Window → TextMesh Pro → Import TMP Essential Resources
Window → Photon → Highlight Free Assets in Asset Store
```

Или через Package Manager:
```
Window → Package Manager → Add package by name
Введите: com.exitgames.fusion (если доступно)
```

### 3.2 URP (Universal Render Pipeline)
Уже должен быть в проекте, но проверьте:
```
Project Settings → Graphics → Scriptable Render Pipeline
Убедитесь, что выбран: UniversalRenderPipelineAsset
```

### 3.3 Addressables
```
Window → Asset Management → Addressables → Groups
```

---

## ▶️ Шаг 4: Запуск сцены

### Вариант A: Главное меню
1. Откройте папку `Assets/Scenes/`
2. Дважды кликните на сцену `MainMenu.unity`
3. Нажмите **Play** (Ctrl+P или верхняя кнопка Play)

### Вариант B: Тренировка с ботами (если существует)
1. Откройте `Assets/Scenes/TrainingMap.unity`
2. Нажмите **Play**

---

## 🛠️ Шаг 5: Тестирование на эмулятор��

### Android (Android Studio)
```bash
# Убедитесь, что Android SDK настроен
File → Build Settings → Android → Build And Run
```

### iOS (Mac only)
```bash
# Требует Xcode на Mac
File → Build Settings → iOS → Build And Run
```

### WebGL (для быстрого тестирования в браузере)
```
File → Build Settings → WebGL → Build And Run
```

---

## 📱 Шаг 6: Проверка управления на мобильном

Если запускаете в редакторе **Game View**:
1. Переключитесь на размер **iPhone** или **Tablet**
2. Используйте **мышь** для имитации сенсорного экрана:
   - Левая кнопка мыши = палец
   - Движение = свайп/камера

Если на реальном устройстве:
1. Подключите устройство через USB
2. Включите **USB Debugging** (Android) или **Developer Mode** (iOS)
3. Нажмите **Build And Run**

---

## 📊 Шаг 7: Проверка производительности

### Профилирование в редакторе
```
Window → Analysis → Profiler
```

Мониторьте:
- **CPU Usage** — должен быть < 70% на мобильном
- **Memory** — должен быть < 500 МБ
- **FPS** — 60 на флагманах, 30 на бюджетных

### Отчёт о профилировании
```
Window → Analysis → Frame Debugger
```

---

## 🔐 Шаг 8: Подключение к Photon Cloud

1. Зарегистрируйтесь на [photonengine.com](https://www.photonengine.com)
2. Создайте приложение (Application ID)
3. В Unity откройте папку `Assets/Photon/PhotonServerSettings.asset`
4. Вставьте свой **Application ID**
5. Теперь можно подключаться к серверам Photon

---

## 🐛 Решение распространённых проблем

### ❌ Ошибка: "No Scene loaded"
**Решение:** Откройте любую сцену из папки `Assets/Scenes/` перед нажатием Play

### ❌ Ошибка: "Shader compilation failed"
**Решение:** Перезагрузите Unity (File → Reload Project)

### ❌ Ошибка: "Memory too low"
**Решение:** Уменьшите качество графики в Settings → Quality

### ❌ Приложение зависает при запуске
**Решение:** Очистите кэш (Library папку)
```bash
rm -rf Library/
# Unity пересоздаст автоматически
```

### ❌ Фиксированный FPS вместо 60
**Решение:** Проверьте в Project Settings → Time
```
Установите: Fixed Timestep = 0.016667 (для 60 FPS)
```

---

## 📂 Основная структура проекта

```
TacticalStrike-Mobile-FPS/
├── Assets/
│   ├── Scripts/           # Весь C# код
│   │   ├── Core/         # Главные менеджеры
│   │   ├── Player/       # Система игрока
│   │   ├── Combat/       # Боевые системы
│   │   ├── Input/        # Мобильное управление
│   │   └── Network/      # Сетевой код (Photon)
│   ├── Scenes/           # Unity сцены
│   ├── Prefabs/          # Переиспользуемые объекты
│   ├── Models/           # 3D модели
│   ├── Materials/        # Материалы и шейдеры
│   ├── Animations/       # Анимации
│   ├── Addressables/     # Асинхронная загрузка
│   └── Resources/        # Ресурсы (текстуры, аудио)
├── Packages/             # Зависимости (Photon Fusion, URP)
├── ProjectSettings/      # Настройки проекта
└── README.md            # Этот файл
```

---

## ✅ Контрольный список первого запуска

- [ ] Клонировал репозиторий
- [ ] Открыл проект в Unity 6
- [ ] Установил зависимости (Photon, URP, Addressables)
- [ ] Открыл сцену MainMenu.unity
- [ ] Запустил Play и вижу главное меню
- [ ] Профилировал производительность (Profiler)
- [ ] Запустил на мобильном эмуляторе (Android Studio / Xcode)
- [ ] Протестировал управление (виртуальный джойстик работает)
- [ ] Подключил Application ID от Photon

---

## 🚀 Следующие шаги после первого запуска

1. **Создать основную архитектуру** (GameManager, NetworkManager, UIManager)
2. **Реализовать мобильное управление** (виртуальный джойстик, кнопки)
3. **Добавить первого персонажа** (модель, анимации, контроллер)
4. **Создать первую карту** (простая геометрия, лайтмапы)
5. **Реализовать систему оружия** (урон, боеприпасы, звуки)
6. **Подключить Photon Fusion** (сетевая синхронизация)
7. **Создать UI** (главное меню, HUD, экран раунда)

---

## 📚 Полезные ссылки

- 📖 [Unity 6 Documentation](https://docs.unity.com)
- 📖 [Photon Fusion Documentation](https://doc.photonengine.com/fusion/current/getting-started/overview)
- 📖 [URP Best Practices for Mobile](https://docs.unity.com/Packages/com.unity.render-pipelines.universal@latest)
- 📖 [Addressables System](https://docs.unity.com/Packages/com.unity.addressables@latest)

---

## 💬 Контакты и поддержка

Если возникают проблемы:
1. Проверьте версию Unity (должна быть 6 или 2022 LTS)
2. Очистите Library папку и пересоздайте проект
3. Проверьте консоль Unity (Window → Console) на ошибки
4. Откройте Issue на GitHub

---

**Версия: 1.0**  
**Последнее о��новление: 2026-09-06**  
**Статус: ✅ Готово к использованию**

---

## 🎯 Быстрый тест прямо сейчас

Если вы уже имеете Unity установленную, выполните эту команду:

```bash
# 1. Клонируйте репозиторий
git clone https://github.com/oallkpral-byte/TacticalStrike-Mobile-FPS.git

# 2. Откройте папку
cd TacticalStrike-Mobile-FPS

# 3. Откройте в Unity (если Unity установлена в PATH)
unity -projectPath . &
```

Успехов! 🚀
