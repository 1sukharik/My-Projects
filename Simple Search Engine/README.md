# Search engine
## Задача:
- Проcтой полнотекстовый поиск над файлами.
- Решение подобных задач предполагает подготовку поискового индекса (набора файлов с различными структурами данных) и поиска по полученным файлам.
- В данной работе требуется реализовать один из самых простых вариантов поискового индекса - инвертировнный индекс.
- Задача полнотекстового поиска так же подразумевает решение проблемы ранжирования (упорядочения найденных по запросу документов). От вас требуется реализовать функцию ранжироавние BM25, а в качестве фактора для нее TF-IDF.
Таким образом вам необходимо реализовать два приложения - индексатор (подготовка поискового индекса) и поиск (программу осуществляющуюу не посредственно поиск по построенному индексу)
## Требования к индексирующей программе:
- Консольное приложение. Структура аргументов командной строки - детали вашей реализации
- Обходить все файлы по определенной директории рекурсивно
- Осуществлять подготовку инвертированного индекса и сопутствующий файлов (если потребуется)
- Основное требование, его размер должен быть оптимизирован, в предположение что количество файлов может быть очень большим (например весь GitHub).
## Требования к поисковой программе:
- Консольное приложение, взаимодействие с пользователем через стандартные потоки ввода и вывода
- Осуществлять поиск по построенному индексу
- Ранжировать найденные документы согласно BM25
- Выдавать в качестве результат список файлов с номерами строк где встречается данное слово
- Поддерживать синтаксис запросов с 'AND' и 'OR'
- Некорректный запрос должен приводить к выводу ошибки
- Поиск регистронезависимый
## Синтаксис запросов
Должен поддерживать скобки а также операции AND и OR (регистр имеет значение). Таким образом в качестве запроса выступают логические выражения. Разделитель между словами - пробел(ы)
Следующие запросы считаются корректными
- "for"
- "vector OR list"
- "vector AND list"
- "(for)"
- "(vector OR list)"
- "(vector AND list)"
- "(while OR for) and vector"
- "for AND and"
Некорректными запросами считаются
- "for AND"
- "vector list"
- "for AND OR list"
- "vector Or list"
