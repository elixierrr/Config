FROM node:20
WORKDIR /app

# Copy file package.json dan package-lock.json untuk install dependencies
COPY package*.json ./

# Install dependencies
RUN npm install

# Install Babel CLI dan Cross-Env secara global
RUN npm install -g @babel/node cross-env

# Copy seluruh file aplikasi ke dalam container
COPY . .

ENV NODE_ENV=development
ENV NODE_PATH=.

# Ekspos port 8080 
EXPOSE 8080

# Jalankan migrasi dan seeding database, lalu jalankan aplikasi
CMD npm run db:migrate && npm run db:seed && npm run dev
