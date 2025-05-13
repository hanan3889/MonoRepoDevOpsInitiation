FROM nginx:stable-alpine

# Copie des fichiers statiques
COPY public/ /usr/share/nginx/html

# Copie de la configuration personnalisée
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose le port 80
EXPOSE 80

# Healthcheck
HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
CMD wget --spider -q http://localhost || exit 1
