## Лабораторная работа 5
***

<h5 align="center">ФЕДЕРАЛЬНОЕ ГОСУДАРСТВЕННОЕ АВТОНОМНОЕ ОБРАЗОВАТЕЛЬНОЕ УЧРЕЖДЕНИЕ ВЫСШЕГО ОБРАЗОВАНИЯ

НАЦИОНАЛЬНЫЙ ИССЛЕДОВАТЕЛЬСКИЙ УНИВЕРСИТЕТ ИТМО



Отчет по лабораторной работе № 5

По дисциплине Информатика

Юшков Андрей Михайлович

Факультет инфокоммуникационных технологий

Группа К3139

Направление подготовки Мобильные и сетевые технологии</h5>

***
## Задание 1 - Автоматизация проверки формата файлов при коммите

Все `hooks` хранятся в директории `.git/hooks`. Первым выполняется файл pre-commit. Он используется для проверки файлов, которые собираются закоммитить. Именно поэтому я буду писать commit здесь

Создаю файл pre-commit

![image](https://github.com/user-attachments/assets/b4b4a704-1229-48ae-891b-d1844ebb0899)

Изменяю права доступа 

![image](https://github.com/user-attachments/assets/686f3972-ecc9-45fb-9d92-8ec601e772f7)

Записываю в файл следующий скрипт

![image](https://github.com/user-attachments/assets/818d8b51-c13d-4a91-b305-04ecd7df06f9)

Далее я создаю пустой  файл `empty-file1.txt` и проверяю его с помощью commit

![image](https://github.com/user-attachments/assets/4b84e984-79d3-4e0d-912b-2f2376d46343)

## Задание 2 - Использование Git Flow в проекте

1. Устанавливаю Git Flow установлен на локальной машине:

```
sudo port install git-flow
```

2. В корне репозитория выполняю инициализацию Git Flow.

```
git flow init
```
![image](https://github.com/user-attachments/assets/1bf2e368-a128-4b9b-973f-0d676e755d76)

3. Создаю ветку для новой функциональности, она называется "task-management":

```
git flow feature start task-management
```
![image](https://github.com/user-attachments/assets/ee49a91f-7458-4ef5-a732-ec32cba7d528)

4. Вношу изменения в код для добавления функционала управления задачами (в файл task_manager.py):

```
def create_task(title, description):
    print(f"Создана новая задача: {title}")
```
![image](https://github.com/user-attachments/assets/45ecfdb7-953b-4cf8-a9fa-e2f31f1fd199)

Выполняю коммит изменения по мере разработки:
![image](https://github.com/user-attachments/assets/1994edc4-869f-49d2-8e1a-29953d0e8108)

5. После завершения разработки функции завершаю feature и объединяю ее с основной веткой:

```
git flow feature finish task-management

```
![image](https://github.com/user-attachments/assets/11fc5ddb-fd8c-4385-91ec-19bc404c00fa)

6. Переключаюсь на ветку "development" и начнаю создание релиза:

```
git checkout development
git flow release start v1.0.0
```
![image](https://github.com/user-attachments/assets/66647c67-409d-4de1-9792-71eaf650543d)

7. Вношу изменения, связанные с релизом (обновляю версию в файле version.txt):

![image](https://github.com/user-attachments/assets/bc360178-588f-4487-a2aa-882a7dccbc41)

8. Завершаю релиз и объединяю его с ветками "development" и "main":

```
git flow release finish v1.0.0
```

9. Создаю hotfix

![image](https://github.com/user-attachments/assets/cff0ba59-82e8-4541-8e49-be6c54936f7e)

10. Вношу изменения для исправления ошибки и коммитите:

```
# Исправление ошибки
git add file_with_error.py
git commit -m "Исправлена критическая ошибка"
```
11. Завершаю hotfix и объединяю его с ветками "development" и "main":

```
git flow hotfix finish hotfix-1.0.1
```

![image](https://github.com/user-attachments/assets/841bd506-2888-4056-a1a1-ffe3c74887f3)


12. Завершение работы и отправка изменений на удаленный репозиторий.

```
git push origin develop
git push origin main
```

![image](https://github.com/user-attachments/assets/d370cc3c-943c-42f3-b772-f150548fbe3b)

![image](https://github.com/user-attachments/assets/628cb71b-1b9f-4217-af2b-38726487f52b)

