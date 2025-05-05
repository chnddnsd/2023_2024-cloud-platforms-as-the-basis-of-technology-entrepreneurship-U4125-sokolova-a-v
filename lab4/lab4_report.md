University: ITMO University(https://itmo.ru/ru/)  
Faculty: FTMI  
Course: Cloud platforms as the basis of technology entrepreneurship (https://itmo-ict-faculty.github.io/cloud-platforms-as-the-basis-of-technology-entrepreneurship/)  
Year: 2024/2025  
Group: U4125  
Author: Sokolova Aleksandra Vladimirovna  
Lab: Lab4  
Date of create: 04.05.2025  
Date of finished: __.05.2025  
___  
### Начальное состояние  
Frontend: Firebase Hosting 
Backend: Cloud Run 
AI: Vertex AI (Image Models)  
База данных: Cloud SQL  
Хранение: Cloud Storage  
![начальное drawio](https://github.com/user-attachments/assets/a43c4f30-e610-45ca-b98f-5eae39b1e3e2)
На данном этапе приложение у приложения serverless-архитектура, что позволяет сделать с упор на минимальные затраты. Веб на Firebase. Cloud Run обрабатывает запросы юзеров, обращается к ИИ-модели. Создаваемые файлы хранятся в Cloud Storage, а для хранения и обработки структурированных данных используется Cloud SQL.   
Для мониторинга на данном этапе ничего не используем.   
Позволяет обеспечить минимальные затраты на старте, возможность автомасштабирования Cloud Run, Vertex AI с оплатой только за количество генераций в день.  

**Расчет стоимости**  
1. Firebase **0$** в месяц при минимальных параметрах
2. Cloud Run **2.88$** в месяц (40 часов)
3. Vertex AI (Image Models) **≈6.08$** в месяц (10 запросов в день)  
4. Cloud SQL (MySQL) **16.80$** в месяц (db-g1-small, 10 GiB)
5. Cloud Storage **0.26$** (10 GiB)  
**Итого: 26.02$**  
___  
### Тестирование партнерами  
В существующую архитектуру добавим балансировщик, а также Cloud Monitoring. Увеличим показатели других компонентов.  
![тест drawio (1)](https://github.com/user-attachments/assets/06648d25-cabd-453c-a4d6-479a015ca3a3)  

**Расчет стоимости**  
1. Cloud Run **13.68$** в месяц (100 часов)
2. Vertex AI (Image Models) **60.83$** в месяц (100 запросов в день)  
3. Cloud SQL (MySQL) **23.50$** в месяц (db-g1-small, 50 GiB)
4. Cloud Storage **1.30$** (50 GiB)
5. Cloud Load Balancing
6. Cloud Monitoring **38.70$**  
**Итого: 136.34$**
___  
### Продовое решение  
Если у нас будет, например, до 5000 ежедневных запросов, то архитектура с Cloud Run останется оптимальной c некоторыми корректировками.  

**Расчет стоимости**  
1. Cloud Run **13.68$** в месяц (100 часов)
2. Vertex AI (Image Models) **60.83$** в месяц (100 запросов в день)  
3. Cloud SQL (MySQL) **23.50$** в месяц (db-g1-small, 50 GiB)
4. Cloud Storage **1.30$** (50 GiB)
5. Cloud Load Balancing
6. Cloud Monitoring **38.70$**  
**Итого: 136.34$**
