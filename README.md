# Видатні греки Харківщини — Геліос

Інформаційно-просвітительська платформа Харківського обласного товариства греків «Геліос».

Аудіо — Web Speech API це браузерний синтезатор, і ти правильно описав його обмеження: роботизований голос, немає перемотки, нестабільна робота. Для якісного озвучення найкращий безкоштовний варіант — ElevenLabs або Google Text-to-Speech. Але є нюанс: вони платні при великих обсягах. Найпростіше рішення для вашого випадку — заздалегідь згенерувати аудіофайли для кожної людини (один раз), завантажити на Google Drive, і додати посилання в колонку Audio. Тоді плеєр просто відтворюватиме готовий файл — якісно і надійно. Генерувати можна безкоштовно через ElevenLabs (до 10 хв/міс безкоштовно) або навіть через Google Translate (є кнопка озвучення)

## Tech Stack
Gitlab - code storage and free hosting
cloudinary.com  - photo hosting
favicon.io - creation of favicons



## Структура

```
index.html    — головна сторінка (каталог постатей)
person.html   — сторінка окремої особи
about.html    — про проєкт
```

## Налаштування Google Sheets

1. Відкрийте Google Таблицю з даними
2. Меню: Файл → Поділитися → Опублікувати в інтернеті
3. Оберіть лист → формат CSV → Опублікувати
4. Скопіюйте отримане посилання
5. Вставте його в обох файлах `index.html` та `person.html` замість рядка:
   ```
   const SHEET_CSV_URL = 'ВАШ_ЛІНК_НА_CSV_ТУТ';
   ```

## Локальний запуск

Використовуйте розширення **Live Server** у VS Code (правий клік на index.html → Open with Live Server).

Або через Python:
```bash
python3 -m http.server 8080
```
Потім відкрийте http://localhost:8080

## Публікація на GitHub Pages

1. Створіть репозиторій на github.com
2. Завантажте всі файли
3. Settings → Pages → Source → main branch → Save
4. Сайт буде доступний на `https://ВАШ-НІК.github.io/НАЗВА-РЕПОЗИТОРІЮ`

## Структура Google Таблиці

Обов'язкові стовпці:
`№, UA_Name, UA_Birth Place, UA_Years, UA_Category, UA_Activity Area, UA_Resume, UA_Key achievements, UA_Places in Kharkiv, UA_Text`

Аналогічно для `GR_` та `EN_` префіксів.

Медіа:
`Photos, Videos, Audio` — посилання через кому.

Фото: посилання на Google Drive (формат share link).
Відео: посилання на YouTube.
