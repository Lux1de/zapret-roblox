<div align="center">

# 🎮 zapret-roblox

**Рабочий обход блокировки Roblox в России**

Основан на [zapret](https://github.com/bol-van/zapret), специально настроен под новые ограничения РКН.  
Исправляет ошибки подключения (Connection Error) и возвращает доступ к сайту и играм.

**Также работает с другими заблокированными сервисами:** YouTube, Discord и многими другими.

---

**Автор:** [Lux1de](https://github.com/Lux1de)  
**Форк репозитория:** [bol-van/zapret](https://github.com/bol-van/zapret)


</div>

> [!WARNING]
> ### ⚠️ АНТИВИРУСЫ
> WinDivert - легальный инструмент для перехвата трафика, необходимый для работы zapret. Антивирусы могут ошибочно считать его угрозой. Драйвер подписан цифровой подписью Microsoft, но может потребоваться добавить в исключения антивируса.

> [!IMPORTANT]
> Все файлы в папке [`bin`](./bin) взяты из официального [zapret-win-bundle](https://github.com/bol-van/zapret-win-bundle/tree/master/zapret-winws). Проверяйте хэши перед использованием!

## 🚀 Быстрый старт

1. **Скачайте последнюю версию** с [releases](https://github.com/Lux1de/zapret-roblox/releases/latest)

2. **Распакуйте** в любую папку без кириллицы и спецсимволов (например: `C:\zapret`)

3. **Запустите** нужный `service.bat` файл от имени администратора

4. **Установите** нужную вам стратегию `1. Install Service`

Видеоинструкция по установке, есть в тг: https://t.me/Lux1de

## 📁 Описание файлов

**`general.bat` и варианты (ALT, FAKE и др.)** - запуск стратегий обхода вручную  
Пробуйте разные варианты, пока не найдёте рабочий для вашего провайдера

**`service.bat`** - управление автозапуском:
- `Install Service` - добавить стратегию в автозапуск Windows
- `Remove Services` - удалить из автозапуска
- `Check Status` - проверить статус работы
- `Run Diagnostics` - диагностика проблем + очистка кэша Discord
- `Check Updates` - проверить обновления
- `Switch Game Filter` - включить/выключить обход для игр (UDP/TCP порты >1023)
- `Switch ipset` - режимы фильтрации IP: `none` / `loaded` / `any`
- `Update ipset list` - обновить список IP-адресов


## ❓ Решение проблем

### Ничего не происходит после запуска

После запуска `general*.bat` должен появиться процесс `winws.exe` в панели задач. Если его нет - запускайте от имени администратора.

### Обход не работает или перестал работать

> [!TIP]
> Стратегии могут переставать работать из-за изменений со стороны РКН. Пробуйте разные варианты `general*.bat` файлов.

1. Запустите `service.bat` → `Run Diagnostics` - проверьте ошибки
2. Убедитесь, что ресурс добавлен в списки (см. раздел ниже)
3. Попробуйте другие стратегии: `ALT`, `FAKE`, `SIMPLE FAKE` и т.д.
4. Если ничего не помогает - сделайте полную переустановку:
   - Сохраните свои изменения в списках
   - Перезагрузите ПК
   - `service.bat` → `Remove Services`
   - Удалите папку zapret
   - Скачайте свежую версию с [releases](https://github.com/Lux1de/zapret-roblox/releases)
   - Распакуйте и протестируйте стратегии заново

### Не работают другие игры/приложения

Отключите фильтры: `service.bat` → `Game Filter` (disabled) и `ipset` (empty)

### Античит блокирует WinDivert

Инструкция по скрытию: [windivert-hide](https://github.com/bol-van/zapret-win-bundle/tree/master/windivert-hide)

### Windows 7: требуется подпись драйвера

Замените `WinDivert.dll` и `WinDivert64.sys` из папки `bin` на файлы из [win7](https://github.com/bol-van/zapret-win-bundle/tree/master/win7)

### WinDivert остался в службах после удаления

```cmd
driverquery | find "Divert"
sc stop [название_службы]
sc delete [название_службы]
```

### Другие проблемы

Создайте issue в [разделе Issues](https://github.com/Lux1de/zapret-roblox/issues)

## � Добавление своих ресурсов

Добавляйте домены и IP в файлы из папки `lists`:

- `list-general.txt` - домены для обхода (поддомены включаются автоматически)
- `list-exclude.txt` - исключения доменов
- `ipset-all.txt` - IP-адреса и подсети
- `ipset-exclude.txt` - исключения IP-адресов

## ⭐ Поддержка

Поставьте звезду ⭐ этому репозиторию, если проект помог вам!

## 📜 Лицензия

Проект распространяется под лицензией [MIT](./LICENSE.txt)

## 💙 Благодарности

Огромная благодарность разработчику [zapret](https://github.com/bol-van/zapret) - [bol-van](https://github.com/bol-van) за создание этого инструмента!
