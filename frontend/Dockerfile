FROM node:17 AS build
WORKDIR /app
COPY ./todo-list/package.json ./package.json 
RUN npm i

COPY ./todo-list ./
RUN npm run build

#!!!

FROM nginx
COPY --from=build /app/dist/index.html /nginx/static/index.html
COPY --from=build /app/dist/static/css /nginx/static/
COPY --from=build /app/dist/static/js /nginx/static/
