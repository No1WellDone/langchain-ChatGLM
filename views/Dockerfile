# build front-end
FROM node:20.15.1-alpine3.20 AS frontend

RUN npm install pnpm -g

WORKDIR /app

COPY ./package.json /app

COPY ./pnpm-lock.yaml /app

RUN pnpm install

COPY . /app

RUN pnpm run build



COPY --from=frontend /app/dist /app/public

EXPOSE 3002

CMD ["pnpm", "run", "preview"]
