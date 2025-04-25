University: ITMO University(https://itmo.ru/ru/)  
Faculty: FTMI  
Course: Cloud platforms as the basis of technology entrepreneurship (https://itmo-ict-faculty.github.io/cloud-platforms-as-the-basis-of-technology-entrepreneurship/)  
Year: 2024/2025  
Group: U4125  
Author: Sokolova Aleksandra Vladimirovna  
Lab: Lab1  
Date of create: 21.04.2025  
Date of finished: __.04.2025  
___
После создания Service Account и виртуальной машины по инструкции к лабораторной работе переходим к выполнению задания по копированию файлов на нашу ВМ.  
1. Создаем папку с помощью команды mkdir
2. С помощью утилиты gsutils смотрим, что файлы лежат в бакете
3. Копируем файлы в созданную папку на нашей ВМ  
4. Проверяем, что файлы лежат в нашей папке  
<img width="468" alt="image" src="https://github.com/user-attachments/assets/65104ab5-7139-4316-b6df-60884141cbfa" />  

Далее меняем права доступа для созданного Service Account с Storage Admin на Compute Viewer
<img width="468" alt="image" src="https://github.com/user-attachments/assets/39f7e3f1-c50a-4b2d-9cf8-edbc1f513508" />  
Пробуем скопировать файлы после того как сменили права доступа:  
<img width="468" alt="image" src="https://github.com/user-attachments/assets/5403f43d-e124-4a81-b1c0-91ef46c0b823" />  
Мы не можем скопировать файлы, так как у нас недостаточно прав, возвращается ошибка.
