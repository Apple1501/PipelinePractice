# Отчёт
Пример [статус бейджа](https://docs.microsoft.com/en-us/azure/devops/pipelines/create-first-pipeline?view=azure-devops&tabs=java%2Ctfs-2018-2%2Cbrowser) с пайплайна:

[![Build Status](https://dev.azure.com/alekseevap0275/prymak/_apis/build/status/Apple1501.PipelinePractice?branchName=master)](https://dev.azure.com/alekseevap0275/prymak/_build/latest?definitionId=3&branchName=master)

## Локальный запуск функциональных и юнит тестов

Для тестирование используется pytest модуль.

С помощью команды устанавливаем pytest:
```shell
   pip install pytest
 ```
Запускаем тестирование и проверяем, что всё работает.
![](./assets/Screenshot_2.png) 

После этого создаём ошибку в коде и убеждаемся, что один из тестов не пройдён.
![](./assets/Screenshot_10.png) 

Для функционального тестирования используем модуль selenium:

```shell
   pip install selenium
 ```
1. Скачиваем драйвер chrome и переносим его в папку с функциональными тестами
2. Запускаем приложение app.py
3. Запускаем тест с помощью команды:

```shell
  pytest tests/functional_tests
```
![](./assets/Screenshot_11.png) 

![](./assets/Screenshot_12.png) 

![](./assets/Screenshot_4.png) 

4. Меняем код и проверяем, что тест вылавливает ошибки

![](./assets/Screenshot_1.png) 

![](./assets/Screenshot_5.png) 

Ошибка найдена, тест не пройден.


## Pipeline - continuous integration (CI) with Azure DevOps

Настраиваем интеграцию с Azure DevOps

Создаём Pipeline. Переходим в пайплайн. Убеждаемся, что все stages выполнены

![](./assets/Screenshot_17.png) 

![](./assets/Screenshot_20.png) 

## Pipeline - continuous deployment (CD) with Azure DevOps

Создаём Web App в Azure

![](./assets/Screenshot_21.png) 

В Azure DevOps создаём Release

![](./assets/Screenshot_25.png) 

Проверяем работу: https://primak-web.azurewebsites.net/

![](./assets/Screenshot_26.png) 

Добавляем тесты в Release

![](./assets/Screenshot_27.png) 

В результате прохождения тестов и выпуска приложения репозиторий GitHub был отмечен зеленой галочкой

![](./assets/Screenshot_23.png) 