FROM python:3.11-slim
# используйте образ, который скачали в прошлом уроке
# и в котором уже установлен Python

LABEL author=${AUTHOR}
COPY . ./churn_app
# скопируйте файлы в Docker
# название директории внутри контейнера: churn_app


WORKDIR churn_app 
# измените рабочую директорию Docker 


RUN pip3 install -r requirements.txt
# инструкция для установки библиотек

VOLUME /models
# указываем, что директория models внутри контейнера будет являться томом

EXPOSE ${APP_PORT}
# инструкция для открытия порта
# используйте порт, который указан в Readme

CMD uvicorn app.churn_app:app --reload --port ${APP_PORT} --host 0.0.0.0
# какая команда должна исполняться при старте контейнера?