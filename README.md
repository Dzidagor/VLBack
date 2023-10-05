# Jira Project 2 Back

Пушить абы как нельзя, без таски коммитов быть не должно, в дев не пушим, учитываем правила.
В терминале:
cd <project path>
git config core.hooksPath hooks

***Как запустить docker-compose.yml на Windows*** 

> Предисловие: В нашем проекте мы запускаем не сам образ, а docker-compose файл, так как наш проект требует postgres, но ниже будет
инструкция для запуска образа.
    
> Перед исполнением шагов убедитесь, что Docker Desktop установлен на вашем компьютере и вы можете взаимодействовать с ним через командную строку.

- Шаг 1: Убедитесь, что файл образа, который используется в docker-compose, 
    и docker-compose файл находятся в одном месте.

- Шаг 2: Убедитесь, что файл образа и docker-compose файл находятся в папке проекта.

- Шаг 3: Откройте командную строку и введите следующую команду: `cd "путь к папке проекта"`
    
`Пример: cd c:\Users\elino\IdeaProjects\jp2`
    
> Если команда использована правильно, то сразу появиться следующая строчка для ввода команд в таком виде: "путь к папке проекта"

> `Пример: c:\Users\elino\IdeaProjects\jp2>`

- Шаг 4: Введите в командную строку: `docker-compose up`

> Если всё прошло удачно, то вы увидите логи и ваша командная строка будет нерабочей.

> Чтобы избежать этого введите команду: `docker-compose up -d`

> Если docker не может найти ваш docker-compose, 
проверьте находится ли docker-compose и образ, 
который он использует, в папке, которую вы указали в шаге 3.

- Шаг 5: Зайдите в Docker Desktop во вкладку Containers. 

> Если всё выполнено правильно и docker-compose файл не имеет ошибок, то там вы увидите docker-compose файл, который имеет статус Running. 

> Развернув его, вы сможете увидеть контейнеры, который созданы на основе образов,которые включены в docker-compose. 

> Если они не имеют ошибок, то их статусы также будут иметь статус Running.
> 
***Как создать и запустить Dockerfile(образ) на Windows***

> Предисловие: Перед исполнением шагов убедитесь, что Docker Desktop установлен на вашем компьютере и вы можете взаимодействовать с ним через командную строку.

- Шаг 1: Убедитесь, что файл образа находится в папке проекта.

- Шаг 2: Откройте командную строку и введите следующую команду: `cd *путь к папке проекта*`

> Пример: `cd c:\Users\elino\IdeaProjects\jp2`
    
> Если команда использована правильно, то сразу появиться следующая строчка для ввода команд в таком виде: `путь к папке проекта>`
>Пример: `c:\Users\elino\IdeaProjects\jp2>`

- Шаг 3: Введите в командную строку: `docker build -t *имя образа, которое вы хотите дать ему* .`

> **Важно**: не забудьте точку в конце и пробел между точкой и именем образа.
> Пример: `docker build -t jp .`

> Если docker не может найти ваш dockerfile, 
    проверьте находится ли dockerfile в папке, которую вы указали в шаге 2.

- Шаг 4: Зайдите в Docker Desktop во вкладку Images. 
> Если всё сделано правильно, то во вкладке Images появится образ с названием, которое было дано в шаге 3.

- Шаг 5: Перейдите обратно в Командную строку и введите: `docker run *имя образа*`

> Если вам нужно подключить порт, то напишите такую команду: `docker run -p порт:порт *имя образа*`

> Пример: `docker run -p 8080:8080 jp`

> Если вы хотите чтобы не показывались логи в командной строке и чтобы командная строка оставалась рабочей, то напишите такую команду: 

> `docker run -d *Имя образа*`

> Если с портом, то: docker run -p порт:порт -d *имя образа*

- Шаг 6: Перейдите в Docker Desktop и откройте вкладку Containers.

> Если вы всё сделали правильно, то там будет контейнер, 
     который имеет во вкладке Images  название вашего образа и статус Running.

Требования:
 - JDK 17
 - maven

1. Сборка проекта:
    - Перейти в директорию проекта
    - Выполнить команду: mvn clean package

2. Запуск проекта:
    - В директории проекта выполнить команду: java -jar target\taskmanager-0.0.1-SNAPSHOT.jar