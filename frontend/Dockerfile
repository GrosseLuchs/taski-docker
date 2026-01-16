FROM node:18

WORKDIR /app

COPY package.json package-lock.json ./
RUN npm cache clean --force && \
    npm install --no-optional --legacy-peer-deps

COPY . .

RUN npm run build

CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]