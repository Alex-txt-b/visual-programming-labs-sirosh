# Отчет по лабораторной работе №3
**Тема:** Технологии визуального программирования. No-code разработка в Bubble
**Студент:** Sasha Sirosh
**Выполненная ачивка:** Ачивка 2. Plugins (Confetti)

---

## 1. Краткое описание выполненного
В рамках работы создано веб-приложение «Трекер привычек и целей» на платформе Bubble. Проведена генерация каркаса приложения через встроенного AI-агента, выполнен анализ Bubble Build Guides с интеграцией системы маркировки приоритетов задач. Ручным способом настроена дизайн-система приложения (глобальная переменная цвета primary-color, кастомный стиль для кнопок, готовый UI-компонент из библиотеки). Спроектирована сущность базы данных Goal с полями различных типов, заполнены тестовые данные через App Data. На отдельной странице goals с помощью AI-инструментов сгенерирован интерфейс и реализован полный CRUD-функционал (Create, Read, Update, Delete) через отдельные Workflows. В качестве ачивки подключен и протестирован сторонний плагин запуска анимации конфетти.

## 2. Исходный AI-промпт (Часть 1)
Создай приложение на тему «Трекер привычек»
Пусть этот сайт будет публичный
Страницу обязательно создай по структуре header + body + footer
Обязательно укажи в заготовке следующую строку: «ТВП: Sirosh»
Добавь несколько интерактивных элементов (реализующих CRUD)

## 3. Ссылка на dev-версию приложения
- https://habitflow-80004.bubbleapps.io/version-test/?debug_mode=true

## 4. Использованные AI-промпты
1. **Генерация каркаса приложения (Часть 1):**
   > «Создай приложение на тему "Трекер привычек". Пусть этот сайт будет публичный. Страницу обязательно создай по структуре header + body + footer. Обязательно укажи в заготовке следующую строку: "ТВП: Sirosh". Добавь несколько интерактивных элементов (реализующих CRUD).»

2. **Проектирование сущности Data (Часть 4.1):**
   > «Спроектируй структуру сущности "Goal" для Bubble: имя Data Type, 4 поля с типами (текст, дата, логический yes/no, число), а также примеры тестовых записей.»

3. **Генерация UI страницы CRUD (Часть 4.2):**
   > «Create a clean and modern page for managing Goals. Add a form at the top to create a new Goal with inputs for name, target count, deadline and Add Goal button. Below add a Repeating Group displaying Goals with Complete and Delete buttons.»

## 5. Освоенные элементы и Workflows
- **Элементы UI:** Header, Repeating Group, Input, Date/Time Picker, Button, Component Library Card, Confetti Animation.
- **Дизайн и стилизация:** вкладка Global, Color Variable (primary-color), кастомный стиль кнопки Custom-Primary-Button.
- **Workflows (CRUD):**
  - **Create:** `When Button Add Goal is clicked` -> `Data -> Create a new thing (Type: Goal)` -> `Reset relevant inputs`.
  - **Read:** Отображение записей в Repeating Group (`Type: Goal`, `Data source: Do a search for Goals`).
  - **Update:** `When Button Complete is clicked` -> `Make changes to Current cell's Goal` (`is_achieved = yes`).
  - **Delete:** `When Button Delete is clicked` -> `Delete Current cell's Goal`.
- **Плагин:** Интеграция действия запуска салюта Trigger Confetti при выполнении цели.

## 6. Исследование идеи (Build Guides)
- Изучен официальный гайд Bubble Build Guides по созданию трекеров задач и привычек.
- Взята идея категоризации задач и визуальной маркировки приоритетов. В карточки добавлен бейдж `🔥 Приоритет: Высокий`.

## 7. Ачивка 2: Plugins
- Установлен и подключен сторонний визуальный плагин Confetti.
- Действие плагина добавлено в workflow кнопки выполнения задачи. При нажатии на кнопку в приложении срабатывает праздничный салют конфетти.
- В ходе защиты готов продемонстрировать изменение параметров плагина в реальном времени.

## 8. Список скриншотов
- `screenshots/01-prompt.png` — генерация каркаса приложения с AI
- `screenshots/02-buildguide-1.png` — исследование Build Guide
- `screenshots/02-buildguide-before.png` — карточки задач до изменений
- `screenshots/02-buildguide-after.png` — карточки после добавления бейджа приоритета
- `screenshots/03-global-variable.png` — создание глобальной переменной цвета
- `screenshots/04-style.png` — создание стиля с глобальной переменной
- `screenshots/05-component.png` — добавление готового UI-компонента
- `screenshots/06-data-type.png` — структура полей сущности Goal
- `screenshots/07-data-records.png` — созданные записи в App Data
- `screenshots/08-workflow-create.png` — проверка создания записи в Preview
- `screenshots/09-workflow-create.png` — workflow создания сущности
- `screenshots/10-workflow-delete.png` — workflow удаления сущности
- `screenshots/12-plugin-1.png` — установленный плагин в панели Plugins
- `screenshots/12-plugin-2.png` — настройка параметров плагина
- `screenshots/12-plugin-3.png` — демонстрация работы салюта в Preview

## 9. Выводы
В ходе выполнения лабораторной работы были освоены базовые возможности no-code платформы Bubble. Очень удобно делать сайт с ИИ-помощником, но в то же время остаётся необходимость точной доработки вручную..