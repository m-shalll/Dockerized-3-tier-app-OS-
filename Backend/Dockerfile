FROM node:latest
WORKDIR /app/Backend
COPY package*.json ./
RUN npm install
#first . current folder on my computer and second . is the current folder inside the container
COPY . .  
RUN mkdir /app/Backend/data
EXPOSE 3000
ENV DB_HOST=localhost
ENV DB_USER=root
ENV DB_PASSWORD=root
ENV DB_NAME=user_db
CMD ["node","server.js"]

