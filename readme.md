## Установка зависимостей
```
pip3 install -r requirements.txt
```

## Авторизация
Возможны два способа аутентификации - с помощью пары логин-пароль или токена. При использовании токена сохранение аудио будет **невозможно**.

Для входа по токену необходимо передать аргумент `token` при запуске:
```
python3 dump.py --token your_token_here
```

## Многопроцессорная загрузка
Количество процессов, создаваемых при дампе, по умолчанию равняется `4*доступные_потоки`.

При загрузке видео - числу, заданному в настройках, но не больше количества доступных потоков.
Такое ограничение введено ввиду отсутствия смысла в спаме лишними процессами при загрузке больших по размеру видео.
Данный лимит может быть отключен в настройках.

## Поддерживаемые для сохранения данные
- [x] Фото
- [x] Аудио
- [x] Видео
- [x] Документы
- [x] Сообщения (txt)
- [x] Вложения понравившихся постов: фото, видео, документы
- [ ] дополнительные форматы для сообщений и прочее, прочее, прочее ;)

## F.A.Q.
**Q: Ошибка vk_api.exceptions.AccessDenied: You don't have permissions to browse user's audio**\
**A:** Попробуйте удалить файл `vk_config.v2.json` и переавторизироваться.

**Q: Ошибка RegexNotFoundError('Unable to extract %s' % _name)**\
**A:** Обновите `youtube_dl`: `pip3 install --upgrade youtube_dl`.
