FROM python:2.7-buster

# Informations sur le mainteneur
LABEL maintainer="nzapanarcisse@gmail.com"

# Copier le code source de l'API dans le conteneur
COPY . /

# Installer les packages requis
RUN apt update -y && \
    apt install -y python-dev python3-dev libsasl2-dev libldap2-dev libssl-dev && \
    pip install flask==1.1.2 flask_httpauth==4.1.0 flask_simpleldap python-dotenv==0.14.0

# Créer un dossier de données et le déclarer comme volume
RUN mkdir /data
VOLUME /data

# Exposer le port 5000 pour interagir avec l'API
EXPOSE 5000

# Commande CMD pour exécuter le script student_age.py
CMD [ "python", "./student_age.py" ]
