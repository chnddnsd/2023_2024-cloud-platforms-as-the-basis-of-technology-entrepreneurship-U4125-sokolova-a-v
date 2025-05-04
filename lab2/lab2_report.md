University: ITMO University(https://itmo.ru/ru/)  
Faculty: FTMI  
Course: Cloud platforms as the basis of technology entrepreneurship (https://itmo-ict-faculty.github.io/cloud-platforms-as-the-basis-of-technology-entrepreneurship/)  
Year: 2024/2025  
Group: U4125  
Author: Sokolova Aleksandra Vladimirovna  
Lab: Lab2  
Date of create: 02.05.2025  
Date of finished: 02.05.2025  
___  
1. Заходим в Cloud Run и создаем дефолтный сервис Hello с портом 8080  
<img width="1280" alt="Снимок экрана 2025-05-02 в 10 23 47" src="https://github.com/user-attachments/assets/b2370e74-44c9-429b-a46e-a95fe4efca21" />
<img width="1280" alt="Снимок экрана 2025-05-02 в 10 27 43" src="https://github.com/user-attachments/assets/e7266f77-17ef-4889-802c-ee0812075dbb" />
2. Перейдем в раздел логи  
<img width="1280" alt="Снимок экрана 2025-05-02 в 10 38 41" src="https://github.com/user-attachments/assets/edb3a3c6-0405-4d6e-99ac-91e334fce2f3" />  
3. Далее перейдем в раздел метрики
<img width="1279" alt="Снимок экрана 2025-05-02 в 10 39 52" src="https://github.com/user-attachments/assets/748c8c3e-8a3c-4c3d-80bd-79157617e005" />
<img width="1280" alt="Снимок экрана 2025-05-02 в 10 40 07" src="https://github.com/user-attachments/assets/e17c3944-6458-455c-b0ee-822c8b2def4c" />
4. Изменим порт нашего сервиса на 8090. Сервис успешно заупстился
<img width="1279" alt="Снимок экрана 2025-05-02 в 10 41 59" src="https://github.com/user-attachments/assets/f7fc4778-1605-4b17-963e-e94f68b2b9f7" />
5. Проверим разделы логи и метрики снова
<img width="1279" alt="Снимок экрана 2025-05-02 в 10 44 28" src="https://github.com/user-attachments/assets/5bd88532-9c4d-4470-a441-99d52ef508c2" />
<img width="1279" alt="Снимок экрана 2025-05-02 в 10 45 06" src="https://github.com/user-attachments/assets/4746285a-ab02-427c-a0d0-128432742b07" />

___  
Выводы:  
1. После смены порта на 8090 в логах появилось сообщение "2025/05/02 07:41:49 Hello from Cloud Run! The container started successfully and is listening for HTTP requests on port 8090",  
что подтверждает, что контейнер успешно переключился на новый порт.  
2. Запись в логах "Default STARTUP TCP probe succeeded after 1 attempt for container "hello-1" on port 8090" также подтверждает, что Cloud Run проверил доступность порта 8090.  
3. Также в логах появилась запись "Cloud RunReplaceServiceasokolova-lab2-00002-89w...response: {…}, serviceName: run.googleapis.com, status: {…}}", что указывает на замену версии через консоль.
4. В разделе метрик видим такие изменения как:  
   — Падение значения Requests Count: до замены порта 0.0133/s, после того как мы изменили порт значение упало до 0, так как порт 8090 еще не начал обрабатывать запросы. После значение вновь увеличлось.  
5. При смене порта также наблюдались изменения метрики Container Instance Count: в момент переключения портов было два активных экземпляра, что отобразилось на диаграмме.
После завершения настройки число эксземпляров вернулось к 0 значению.
6. Также в момент переключения значение метрики Container memory utilization также упало, так как останаливается старый контейнер и запускаются новые.
