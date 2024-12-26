## Задание 1 - Автоматизация проверки формата файлов при коммите

Все `hooks` хранятся в директории `.git/hooks`. Первым выполняется файл pre-commit. Он используется для проверки файлов, которые собираются закоммитить. Именно поэтому я буду писать commit здесь

Создаю файл pre-commit
![image](https://github.com/user-attachments/assets/b4b4a704-1229-48ae-891b-d1844ebb0899)

Изменяю права доступа 
![image](https://github.com/user-attachments/assets/686f3972-ecc9-45fb-9d92-8ec601e772f7)

Записываю в файл следующий скрипт
![image](https://github.com/user-attachments/assets/818d8b51-c13d-4a91-b305-04ecd7df06f9)

Далее я создаю пустой  файл '''empty-file.txt''' и проверяю его с помощью commit

![image](https://github.com/user-attachments/assets/4b84e984-79d3-4e0d-912b-2f2376d46343)
