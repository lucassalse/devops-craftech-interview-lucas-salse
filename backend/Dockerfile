FROM python:3.7-slim-buster

# seteamos el directorio de trabajo
WORKDIR /usr/src/app

# seteamos variables de entorno
# Evita copiar pyc files y mostrar el stdout y stderr
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

COPY ./requirements.txt /usr/src/app

# instalamos las dependencias necesarias y copiamos los requirements.txt
RUN apt update && apt install -y \
    gcc \
    graphviz-dev && \
    pip install --upgrade pip \
    pip install -r requirements.txt && \
    apt autoremove -y \
    gcc \
    graphviz-dev

# copiamos el proyecto
COPY . /usr/src/app

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]