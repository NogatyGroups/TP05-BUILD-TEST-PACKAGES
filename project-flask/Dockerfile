# Utiliser l'image officielle de Python comme image de base
FROM python:3.9

# Définir le répertoire de travail dans le conteneur
WORKDIR /app

RUN ls -la
RUN pwd
# Copier requirements.txt dans le répertoire de travail
COPY requirements.txt ./

# Installer les dépendances
RUN pip install --no-cache-dir -r requirements.txt

# Copier le reste du code de l'application dans le répertoire de travail
COPY . .

# Exposer le port sur lequel l'application s'exécute
EXPOSE 5000

# Démarrer l'application
CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:5000", "app:app"]
