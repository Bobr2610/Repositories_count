[![Repositories](https://raw.githubusercontent.com/Bobr2610/Repositories_count/main/counter.png?v=0)](https://github.com/Bobr2610/Repositories_count)

# Repository Counter

Счётчик репозиториев — показывает количество публичных репозиториев владельца (пользователя или организации) на GitHub.

---

## Как использовать

### 1. Форк и настройка на GitHub

1. Создайте **новый репозиторий** на GitHub (или используйте существующий).
2. Залейте содержимое этой папки в репозиторий (в ветку `main`).
3. В **README.md** замените `OWNER` и `REPO` на ваш логин и имя репозитория в ссылке на бейдж (вверху файла).  
   Пример: если ваш репо `https://github.com/YourName/my-project`, то строка будет:
   ```markdown
   [![Repositories](https://raw.githubusercontent.com/YourName/my-project/main/counter.png?v=0)](https://github.com/YourName/my-project)
   ```

### 2. Personal Access Token

1. [GitHub → Settings → Developer settings → Personal access tokens](https://github.com/settings/tokens)
2. Создайте токен с правом **`read:user`** (или `repo` для полного доступа)
3. Скопируйте токен (он показывается один раз)

### 3. Секрет в репозитории

1. Ваш репо → **Settings** → **Secrets and variables** → **Actions**
2. **New repository secret**
3. Имя: `TRAFFIC_TOKEN`
4. Значение: вставьте токен из шага 2

### 4. Папка theme

В репозитории должна быть папка **`theme/`** с файлами `0.png` … `9.png` (цифры для счётчика).  
Их можно взять из оригинального репозитория:

- [Views_Counter_with_custom_images — theme](https://github.com/Bobr2610/Views_Counter_with_custom_images/tree/main/theme)  
  Скачайте папку `theme` и положите в корень вашего репо.

### 5. Запуск

- **По расписанию:** workflow запускается каждый час и при push (кроме изменений только в `counter.png`, `theme/`, `README.md`).
- **Вручную:** **Actions** → **Update Repository Counter** → **Run workflow**.

После первого успешного запуска в README подставится актуальная ссылка на картинку с `?v=...` — её не нужно менять вручную.

---

Основано на [Views_Counter_with_custom_images](https://github.com/Bobr2610/Views_Counter_with_custom_images).
