# Usar la imagen oficial de Python
FROM python:3.9-slim

# Establecer el directorio de trabajo dentro del contenedor
WORKDIR /app

# Copiar los archivos de requerimientos y el código de la app
COPY requirements.txt /app/
RUN pip install psycopg2-binary
RUN pip install -r requirements.txt

COPY . /app/

# Exponer el puerto que usa Django
EXPOSE 8000

# Comando para correr la aplicación Django
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
