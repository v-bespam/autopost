<div id="header" align="center">
  <img src="https://media.giphy.com/media/M9gbBd9nbDrOTu1Mqx/giphy.gif" width="100"/>
</div>

# Бот для автоматической публикации сообщений из Telegram в ВКонтакте

Этот проект представляет собой скрипт на Python, который автоматически публикует сообщения из Telegram-канала или чата в указанную группу ВКонтакте. Он поддерживает различные типы контента, включая текст, изображения, видео и ссылки.

## Зачем нужен этот проект ?

Многие пользователи и администраторы сообществ сталкиваются с необходимостью дублирования контента между различными платформами. Это может быть рутинной и трудоемкой задачей. Данный скрипт автоматизирует этот процесс, экономя время и уменьшая вероятность ошибок при копировании данных вручную.

## Как работает скрипт ?

1. **Получение данных из Telegram:** Проект использует библиотеку `aiogram` для взаимодействия с Telegram API. Это позволяет получать сообщения и медиафайлы из указанных чатов или каналов.
2. **Обработка медиа-контента:** С помощью `aiogram-media-group`, `moviepy` и `rlottie-python` происходит обработка и подготовка медиафайлов для дальнейшей отправки.
3. **Отправка данных в ВКонтакте:** Библиотека `vk-api` используется для взаимодействия с API ВКонтакте, что позволяет загружать и отправлять медиафайлы и сообщения на указанные страницы или группы.
4. **Конфигурация и управление:** Файл `.env` используется для хранения конфиденциальных данных и ключей API, обеспечивая безопасное управление параметрами приложения.

## Структура проекта

```
autoposting
├── main
│   ├── LICENSE           # Лицензия проекта
│   ├── main.py           # Основная логика 
│   ├── .env              # Конфигурационный файл для учетных данных API
│   ├── Примеры           # Примеры работы бота
├── requirements.txt      # Необходимые библиотеки для проекта
└── README.md             # Документация по проекту
```

## Какие медиафайлы может пересылать бот ?

Бот предназначен для пересылки различных типов медиафайлов из Telegram в ВКонтакте. Вот список медиафайлов, которые бот может обрабатывать и пересылать:

1. **Текстовые сообщения**:
   - Простые текстовые сообщения без медиафайлов.
2. **Изображения**:
   - Фотографии в различных форматах (JPEG, PNG и др.).
3. **Видео**:
   - Видеофайлы в популярных форматах (MP4 и др.).
4. **Аудио**:
   - Голосовые сообщения и музыкальные файлы.
5. **Документы**:
   - Файлы различных типов, включая PDF, DOCX, XLSX и другие.
6. **Анимации**:
   - GIF-анимации и анимированные стикеры.
7. **Медиа-группы**:
   - Группы медиафайлов, включающие комбинации изображений и видео, отправленные как единое сообщение.

### Пример использования

- **Изображения**: Если пользователь отправляет в Telegram фото с описанием, бот автоматически пересылает это изображение и текст на указанную страницу или группу ВКонтакте.
- **Видео**: Видео с Telegram пересылается в соответствующем формате в ВКонтакте, сохраняя оригинальное качество.
- **Документы**: Важные файлы или документы пересылаются для удобного доступа участников группы ВКонтакте.
- **Голосовые сообщения**: Голосовые записи из Telegram пересылаются как аудиофайлы в ВКонтакте.

Таким образом, скрипт поддерживает широкий спектр медиафайлов, обеспечивая гибкость и удобство при переносе контента между платформами. 

## Установка и запуск проекта

1. **Склонируйте репозиторий:**

   ```bash
   git clone https://github.com/love-angelll/autopost
   cd autopost
   ```

2. **Установите необходимые зависимости:**

   Убедитесь, что у вас установлен `pip`. Затем выполните команду:

   ```bash
   pip install -r requirements.txt
   ```

3. **Настройка окружения:**

   Создайте файл `.env` в корне проекта и добавьте необходимые переменные окружения. Пример файла `.env`:

   ```env
   VK_API_TOKEN=YOUR_VK_API_TOKEN
   TELEGRAM_API_TOKEN=YOUR_TELEGRAM_API_TOKEN
    TELEGRAM_CHANNEL_USERNAME=YOUR_TELEGRAM_CHANNEL_USERNAME
   VK_GROUP_ID=YOUR_VK_GROUP_ID
   ```

4. **Запуск приложения:**

   Приложение можно запустить с помощью следующей команды:

   ```bash
   python app.py
   ```

#### Подробности реализации

- **`aiogram`**: Асинхронная библиотека для работы с Telegram Bot API.
- **`aiogram-media-group`**: Расширение для обработки групповых медиа-сообщений в Telegram.
- **`aiohttp`**: Асинхронная библиотека HTTP-клиента/сервера.
- **`python-dotenv`**: Позволяет загружать переменные окружения из файла `.env`.
- **`vk-api`**: Библиотека для работы с API ВКонтакте.
- **`rlottie-python`**: Библиотека для работы с анимациями.
- **`moviepy`**: Библиотека для редактирования видео.

## Особенности

- Поддерживает публикацию текстовых сообщений, изображений, видео и ссылок.
- Настраивается с помощью простого файла TOML.
- Регистрирует активность, что помогает в отладке и мониторинге.

## Содействие

Не стесняйтесь отправлять проблемы или запросы на исправление, если у вас есть какие-либо вопросы то пишите в соц. сетях.

[![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/iv_frunza)
[![VK Основной](https://img.shields.io/badge/VK%20Основной-4A76A8?style=for-the-badge&logo=vk&logoColor=white)](https://vk.com/iv.frunza)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/iv.frunza)

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------


