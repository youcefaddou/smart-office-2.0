# Utilisation d'une image Nginx légère et sécurisée
FROM nginx:alpine

# Suppression de la page par défaut de Nginx
RUN rm -rf /usr/share/nginx/html/*

# Copie des fichiers web locaux vers le conteneur (nous créerons un index.html plus tard)
# COPY src/ /usr/share/nginx/html/

# Exposition du port 80
EXPOSE 80

# Démarrage du service
CMD ["nginx", "-g", "daemon off;"]