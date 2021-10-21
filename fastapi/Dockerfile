FROM python:3.9.6-alpine

ARG APP_PATH=/opt/app
ARG APP_USER=fastapi

RUN adduser -h ${APP_PATH} -s /bin/sh -D ${APP_USER} && \
    mkdir -p ${APP_PATH} && \
    chown ${APP_USER}:${APP_USER} ${APP_PATH} && \
    chmod 755 ${APP_PATH}

USER ${APP_USER}
WORKDIR ${APP_PATH}

ENV PATH="${APP_PATH}/.local/bin:${PATH}"

RUN pip3 install fastapi uvicorn

COPY --chown=${APP_USER}:${APP_USER} ./files/main.py .

CMD ["uvicorn", "--host", "0.0.0.0", "--port", "8080", "main:app"]