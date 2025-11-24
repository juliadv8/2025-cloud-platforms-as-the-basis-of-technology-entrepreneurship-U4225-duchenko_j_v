University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FTMI](https://ftmi.itmo.ru)  
Course: [Cloud platforms as the basis of the technology entrepreurship](https://itmo-ict-faculty.github.io/cloud-platforms-as-the-basis-of-technology-entrepreneurship/)   
Year: 2025/2026   
Group: U4225  
Author: Duchenko Yulia Viktorovna  
Lab: Lab2  
Date of create: 24.11.2025   
Date of finished: ---.11.2025 

## Отчет по лабораторной работе №2 
## "Исследование Cloud Run"

Во время выполнения практического задания сделала следующие шаги:
1. На основе предоставленного дефолтного сервиса «Hello» создала новый сервис Cloud Run - Hello-jd и установила минимальные параметры:
- минимальное количество инстансов — 0,
- максимальное количество инстансов — 2,
- объём памяти 128 MiB,
- 1 vCPU,
- доступ без аутентификации (Allow unauthenticated), чтобы сервис был доступен по публичному URL.
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab2/img/l2_scr.png)

2. После деплоя сервис успешно развернулся и для проверки работоспособности сервиса была выполнена серия запросов по выданному URL. 
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab2/img/l2_scr1.png)

3. После чего изучила логи и метрик сервиса, которые включали: 
- записи о старте контейнера,
- HTTP-запросы к сервису (метод GET, код ответа 200),
- временные метки запросов и информация о ревизии, обработавшей запрос,
- факт поступления запросов,
- успешную обработку запросов без ошибок,
- использование ресурсов (CPU/Memory),
- задержку обработки (latency) для отдельных запросов.
Таким образом, было продемонстрировано, как с помощью логов Cloud Run можно контролировать работу сервиса и диагностировать его состояние, 
а с помощью метрик отслеживать нагрузку на сервис и его производительность.
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab2/img/l2_scr2.png)
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab2/img/l2_scr3.png)

4. В разделе настроек контейнера изменила параметр Container port с значения 8080 на 8090. 
После сохранения изменений и деплоя была автоматически создана новая ревизия сервиса Cloud Run. 
После применения изменений сервис продолжил корректно отвечать по тому же внешнему URL. Ошибок (таких как 502 Bad Gateway) при этом не возникло. 
Это можно объяснить тем, что тестовый сервис использует значение порта из переменной окружения PORT, которую Cloud Run автоматически обновляет при 
изменении настроек контейнерного порта. Соответственно, приложение стало слушать новый порт 8090, а платформа начала направлять трафик на этот порт, 
что обеспечило сохранение работоспособности.
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab2/img/l2_scr4.png)

5. Через интерфейс Manage traffic попробовала разные варианты распределения трафика: 100% трафика на старую\новую ревизию, 50% / 50%.
Во всех вариантах сервис продолжал корректно отвечать по одному и тому же URL.
Различия были заметны на уровне логов: при анализе журналов запросов отображалось, какая именно ревизия обработала тот или иной запрос.

![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab2/img/l2_scr5.png)
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab2/img/l2_scr6.png)

6. Удалила все созданные сервисы.
