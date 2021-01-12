### Мини-проект - ChatService
Личные сообщения - один из неотъемлемых компонентов почти любого социального сервиса.

Задача целиком творческая (руководитель вам сказал "делай, как хочешь"), вот требования:

1. Должны быть чаты (чат - это общение с одним человеком, т.н. `direct messages`)
2. Можно создавать чаты, удалять их, получать список имеющихся чатов
3. В каждом чате есть сообщения от 1 до нескольких (см. раздел ниже)
4. Имеется возможность создавать сообщения, редактировать их и удалять (для простоты - можно удалять и свои, и чужие)
5. В каждой чате есть прочитанные и не прочитанные сообщения

Пользователь должен иметь возможность:

1 . Получить информацию о количестве непрочитанных чатов (например, service.getUnreadChatsCount) - это количество чатов, в каждом из которых есть хотя бы одно непрочитанное сообщение
2. Получить список чатов (например, service.getChats) - где в каждом чате есть последнее сообщение (если нет, то пишется нет сообщений)
3. Получить список сообщений из чата, указав (после того, как вызвана данная функция, все отданные сообщения автоматически считаются прочитанными):
    - id чата
    - id последнего сообщения, начиная с которого нужно подгрузить более новые
    - количество сообщений
4. Создать новое сообщение
5. Удалить сообщение (при удалении последнего сообщения в чате весь чат удаляется)
6. Создать чат (чат создаётся тогда, когда пользователю, с которым до этого не было чата, отправляется первое сообщение)
7. Удалить чат (целиком удаляется все переписка)

Важный момент: чтобы отделять одного пользователя от другого, передавайте во все функции первым параметром id пользователя (например, service.getChats(999) - все чаты для пользователя с id=999)

Старайтесь по максимуму использовать lambda-функции (которые напишите сами) и extension-функции (которые есть в составе `Iterable`, `Collection`, `List`).

Расчёт статистики должен старайтесь производить как цепочку вызова lambda-функций (попробуйте обойтись `for`, `while` и `do-while`).

Подсказки:
1. Сообщения могут быть входящими и исходящими (причём то, что для одного пользователя входящее, для другого исходящее
2. Непрочитанными могут быть как входящие сообщений (тогда они участвуют в подсчёте статистики непрочитанных для получателя) так и отправленные (тогда они не участвуют в подсчёте статистики для отправителя)