# Используем официальный образ Node.js
FROM node:latest

# Добавляем метаданные к образу
LABEL description="A Dockerfile for building and serving a Docsify site."

# Копируем папку с документацией из контекста сборки (frontend/docs)
# в папку /docs внутри контейнера.
COPY /docs /docs

# Устанавливаем рабочую директорию внутри контейнера
WORKDIR /docs

# Устанавливаем docsify-cli глобально
RUN npm install -g docsify-cli@latest

# Сообщаем Docker, что контейнер будет слушать порт 3000
EXPOSE 3000

# Команда по умолчанию для запуска сервера docsify.
# Он будет обслуживать файлы из текущей рабочей директории (/docs).
CMD ["docsify", "serve", "."]
