FROM python:3.11-slim

LABEL author=${AUTHOR}
COPY . ./simple_fast_api
WORKDIR simple_fast_api 
RUN pip3 install -r requirements.txt

VOLUME /speeches
# указываем, что директория speeches внутри контейнера будет являться томом
# на этапе сборки docker создаст необходимые файлы на самой виртуальной машине
# в директории /var/lib/docker/volumes/

EXPOSE ${APP_PORT}
# эта инструкция указывает образу, 
# что порт 1702 должен быть открыт 'снаружи'

CMD uvicorn app.main:app --host  0.0.0.0 --port ${APP_PORT}
