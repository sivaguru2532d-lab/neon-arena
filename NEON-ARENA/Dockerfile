FROM node:22-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM node:22-alpine
WORKDIR /app
ENV NODE_ENV=production
COPY package*.json ./
RUN npm ci --omit=dev && npm install --no-save tsx
COPY --from=build /app/dist ./dist
COPY --from=build /app/server ./server
RUN mkdir -p data
VOLUME ["/app/data"]
EXPOSE 3001
CMD ["npm","start"]
