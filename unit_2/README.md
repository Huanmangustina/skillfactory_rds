# Skillfactory_RDS
 ##UNIT 2
 
→ задача проекта:
Суть проекта — отследить влияние условий жизни учащихся в возрасте от 15 до 22 лет на их успеваемость по математике, чтобы на ранней стадии выявлять студентов,
находящихся в группе риска.

→ основные цели и задачи проекта;
Чтобы определиться с параметрами будущей модели, проведите разведывательный анализ данных и составьте отчёт по его результатам. 

→ краткую информацию о данных;

→ этапы работы над проектом:

Провести первичную обработку данных. 
Так как данных много, стоит написать функции, которые можно применять к столбцам определённого типа.
Посмотреть на распределение признака для числовых переменных, устраните выбросы.
Оценить количество уникальных значений для номинативных переменных.
По необходимости преобразуйте данные
Проведите корреляционный анализ количественных переменных
Отберите не коррелирующие переменные.
Проанализируйте номинативные переменные и устраните те, которые не влияют на предсказываемую величину (в нашем случае — на переменную score).


→ ответы на вопросы саморефлексии:

1. Какова была ваша роль в команде?
аналитик
2. Какой частью своей работы вы остались особенно довольны?

построение графиков

3. Что не получилось сделать так, как хотелось? Над чем ещё стоит поработать?

Найдены не все статистически значимые различия. 



основные итоги работы:

Данные достаточно чистые: 
количество пропущенных значений вырируется от 1% до 11% Есть 3 переменные данные по которым есть полностью . 
Ошибки обнаружены в F_edu family_rel 
переменная absences содержит 2 аномальных значения (рекомендуется поменять на медиану,
с целью сохранения информации в других предикторах.)
    Послед подробного осмотра принято решение:
удалить пропуски из целевой переменной за ненадобностью.
оставить значение 0 в score для выяснения возможности моделирования в этих случаях.
    В результате корреляционного анализа: 
обнаружена сильная обратная связь studytime и studytime_granular, второй удален за ненадобностью 
обнаружена линейная зависимость между F_edu M_edu которую можно использовать для создания нового
значимого признака и взаимного восстановления пропусков.
исключены переменные с коэффициенотом корреляции менее 0.1 по модулю как самые бесперсперктивные на этапе EDA
    Анализ номинативных и смешанных переменных с помощью boxplot  позволил выделить значимые признаки.

для моделирования рекомендуется использовать колонки 
'sex','failures', 'M_edu', 'M_job', 'age', 'go_out', 'study_time', 'F_edu', 'F_job'
                              'travel_time', 'health', 'absences', 'highter', 'romantic'
 эти данные представляют наибольший интерес.


