# Домашнее задание к занятию "`Teamcity`" - `Бакулев Евгений`

### Подготовка к выполнению

1. В Yandex Cloud создайте новый инстанс (4CPU4RAM) на основе образа jetbrains/teamcity-server.
2. Дождитесь запуска teamcity, выполните первоначальную настройку.
3. Создайте ещё один инстанс (2CPU4RAM) на основе образа jetbrains/teamcity-agent. Пропишите к нему переменную окружения SERVER_URL: "http://<teamcity_url>:8111".
4. Авторизуйте агент.

![Скриншот](https://github.com/garrkiss/teamcity/blob/main/img/%D0%9F%D0%BE%D0%B4%D0%B3%D0%BE%D1%82%D0%BE%D0%B2%D0%BA%D0%B0/%D0%92%D0%B8%D1%80%D1%82%D1%83%D0%B0%D0%BB%D0%BA%D0%B8.png)

![Скриншот](https://github.com/garrkiss/teamcity/blob/main/img/%D0%9F%D0%BE%D0%B4%D0%B3%D0%BE%D1%82%D0%BE%D0%B2%D0%BA%D0%B0/a%D0%B3%D0%B5%D0%BD%D1%82.png)

5. Сделайте fork репозитория. [FORK](https://github.com/garrkiss/example-teamcity)
6. Создайте VM (2CPU4RAM) и запустите playbook.

![Скриншот](https://github.com/garrkiss/teamcity/blob/main/img/%D0%9F%D0%BE%D0%B4%D0%B3%D0%BE%D1%82%D0%BE%D0%B2%D0%BA%D0%B0/ansible.png)


### Основная часть

1. Создайте новый проект в teamcity на основе fork.
![Скриншот](https://github.com/garrkiss/teamcity/blob/main/img/Project.png)
2. Сделайте autodetect конфигурации.
![Скриншот](https://github.com/garrkiss/teamcity/blob/main/img/autodetect.png)

3. Сохраните необходимые шаги, запустите первую сборку master.
4. Поменяйте условия сборки: если сборка по ветке master, то должен происходит mvn clean deploy, иначе mvn clean test.
5. Для deploy будет необходимо загрузить settings.xml в набор конфигураций maven у teamcity, предварительно записав туда креды для подключения к nexus.
6. pom.xml необходимо поменять ссылки на репозиторий и nexus.
7. Запустите сборку по master, убедитесь, что всё прошло успешно и артефакт появился в nexus.
8. Мигрируйте build configuration в репозиторий.
9.  Создайте отдельную ветку feature/add_reply в репозитории.
10. Напишите новый метод для класса Welcomer: метод должен возвращать произвольную реплику, содержащую слово hunter.
11. Дополните тест для нового метода на поиск слова hunter в новой реплике.
12. Сделайте push всех изменений в новую ветку репозитория.
13. Убедитесь, что сборка самостоятельно запустилась, тесты прошли успешно.
14. Внесите изменения из произвольной ветки feature/add_reply в master через Merge.
15. Убедитесь, что нет собранного артефакта в сборке по ветке master.
16. Настройте конфигурацию так, чтобы она собирала .jar в артефакты сборки.
17. Проведите повторную сборку мастера, убедитесь, что сбора прошла успешно и артефакты собраны.
18. Проверьте, что конфигурация в репозитории содержит все настройки конфигурации из teamcity.
19. В ответе пришлите ссылку на репозиторий.

![Скриншот](https://github.com/garrkiss/Jira/blob/main/img/bug.png)
![Скриншот](https://github.com/garrkiss/Jira/blob/main/img/all.png)

[Workflow Bug](https://github.com/garrkiss/Jira/blob/main/files/Bug.xml)
[Workflow All](https://github.com/garrkiss/Jira/blob/main/files/All.xml)