# docker

## run container by image
```docker run <имя_образа> ```

### run as a daemon
```docker run -d <имя_образа> ```

### интерактивно в терминале
```docker run -it <имя_образа> ```

### others
```
docker run <параметр запуска> -p <порт_хоста>:<контейнерный_порт> <имя_образа>
docker run <параметр запуска> -v <путь_на_хосте>:<путь_в_контейнере> <имя_образа>
docker run <параметр запуска> -p <порт_хоста>:<контейнерный_порт> -v <путь_на_хосте>:<путь_в_контейнере> --name <имя_контейнера> <имя_образа> 
```

## build by Dockerfile
```docker build <путь_к_Dockerfile> (.) -t <имя_образа>:<тег> ```

## показать список активных контейнеров
```docker ps ```

## показать все контейнеры, включая остановленные
```docker ps -a ```

## остановить контейнер
```docker stop <идентификатор_контейнера_или_имя_контейнера> ```

## удалить контейнер
```docker rm <идентификатор_контейнера_или_имя_контейнера> ```

## загрузить образ из Docker Hub
```docker pull <имя_образа> ```

## показать список всех локальных образов
```docker images ```

## удалить локальный образ
```docker rmi <идентификатор_образа> ```


# Dockerfile

## Используем базовый образ с Python
```FROM python:3.8 ```

## теги
```LABEL maintainer="mail@gmail.com" ```

## Указываем рабочую директорию
```WORKDIR /app ```

## Копируем зависимости в образ
```
COPY requirements.txt .
RUN pip install -r requirements.txt 
```

## копируем из внешнего источника
```ADD https://some-site/vid1.mp4 /app```

## Устанавливаем еще зависимости
```RUN pip install flask ```

## Копируем исходный код в образ
```COPY . /app ```

## Указываем порт для проброса
```EXPOSE 8000```

## задать переменные среды
```ENV SECRET="secret" ```

## Определяем команду для запуска приложения
```CMD ["python", "app.py"] ```

## always point host 0.0.0.0 for web-app
```CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "80"]```

# usefull links
You may be using [usefull links 1](https://learn.microsoft.com/ru-ru/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile).



# .dockerignore