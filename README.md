# Mapping вузов платформы проекта "Твой Ход"
## Задача
1. Сделать бэкап таблицы **educational_institutions** (на случай непредвиденных ошибок).
2. В таблице **educational_institutions** перезаписать строки из файла **mapping.csv** по следующему правилу:
    - если *id* из **mapping.csv** уже есть в *id* **educational_institutions**, то перезаписать значения полей для этой строки из **mapping.csv** (поля *web_address*, *phone*, *director_fio*, *email*, *address_fact*, *legal_org_type*, *municipal_unit_id*, *oktmo*, *type*, *country_id*, *okato* заполнить **null** значениями);
    - если *id* из **mapping.csv** нет в *id* **educational_institutions**, то добавить запись со значениями из **mapping.csv** (поля *web_address*, *phone*, *director_fio*, *email*, *address_fact*, *legal_org_type*, *municipal_unit_id*, *oktmo*, *type*, *country_id*, *okato* заполнить **null** значениями);
3. В таблице *users* заменить текущие **school_id** на **новые id** с помощью файла **mapping.csv** (если для старого school_id учебного заведения нет соответствия в новом списке, то поставить **null** вместо нового id).
4. В таблице *educational_institution_user* заменить текущие **educational_institution_id** на **новые id** с помощью файла **mapping.csv**.
5. Удалить из таблицы **educational_institutions** записи, *id* которых нет в **mapping.csv**.
## Пояснительная записка
### new_db.csv
Новая таблица вузов для БД
#### Поля:
 - id - id учебного заведения
 - legal_inn - ИНН учебного заведения
 - legal_ogrn - ОГРН учебного заведения
 - legal_kpp - КПП (код причины поставновки) учебного заведения
 - name - Полное наименование учебного заведения 
 - short_name - Краткое наименование учебного заведения
 - legal_address - Юридический адрес учебного заведения
 - region - id региона учебного заведения
 - district_id - id федерального округа 
 - branch - флаг, является ли учебного заведение филиалом
### mapping.csv
Таблица с итоговым mapping'ом вузов платформы
#### Поля:
 - old_id - id учебного заведения из старой таблицы БД платформы
 - new_id - id учебного заведения из новой таблицы **new_db.csv**
### mapping_with_names.csv
Таблица с итоговым mapping'ом вузов платформы с указанием названий (таблица прикладывается для валидации работы алгоритма)
#### Поля:
 - old_id - id учебного заведения из старой таблицы БД платформы
 - new_id - id учебного заведения из новой таблицы **new_db.csv**
 - old_name - полное наименование учебного заведения из старой таблицы БД платформы
 - new_name - полное наименование учебного заведения из новой таблицы **new_db.csv**

Алгоритм составления список см. в [algorithms.md](algorithms.md)