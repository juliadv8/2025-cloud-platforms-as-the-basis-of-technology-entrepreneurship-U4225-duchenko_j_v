University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FTMI](https://ftmi.itmo.ru)  
Course: [Cloud platforms as the basis of the technology entrepreurship](https://itmo-ict-faculty.github.io/cloud-platforms-as-the-basis-of-technology-entrepreneurship/)   
Year: 2025/2026   
Group: U4225  
Author: Duchenko Yulia Viktorovna  
Lab: Lab1  
Date of create: 18.11.2025   
Date of finished: __.11.2025 

## Отчет по лабораторной работе №1 
## "Обзор Google Cloud и исследование основных сервисов."

Во время выполнения практического задания сделала следующие шаги:

1. Создала Service Account с ролью Storage Admin
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr1.png )
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr2.png)
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr7.png)

2. Создала Compute Engine VM
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr5.png )

3. Подключилась к VM через SSH и выполнила через команду gsutil копирование файлов на мою VM.
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr10.png )
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr11.png )

4. Изменила права доступа Service Account на Compute Viewer
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr12.png )

5. Повторила операции с прошлого шага уже с новыми правами
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr14.png )
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr15.png )
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr16.png )
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr17.png )
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr18.png )

В итоге получилось, что бакет имеет дополнительные IAM разрешения на уровне ресурса, которые предоставляют права чтения для service account. А также роль Compute Viewer разрешает:
- Просмотр списка бакетов
- Просмотр метаданных объектов
- Чтение конфигурации ресурсов

При этом роль Compute Viewer не разрешает выполнить:
- Запись в Cloud Storage
- Управление IAM политиками
- Создание/удаление объектов


6. Удалила VM
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr19.png )
![](https://github.com/juliadv8/2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-duchenko_j_v/blob/main/Lab1/img/l1_scr20.png )
