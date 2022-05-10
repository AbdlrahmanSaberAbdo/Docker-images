# first stage of building angular image
FROM node:slim as build

# -p: if folder is exist will not created it, if it's not exist will not create the folder
RUN mkdir -p /app

WORKDIR /app

COPY package.json /app/
RUN npm install

COPY . /app/
RUN npm run build --prod

# second stage
FROM nginx:alpine

# /app/dist/docrize-app: this path that we make it in first stage,
# when run build --prod command it'll create a folder called dist and another folder with same name of an app
COPY --from=build /app/dist/dockrize-app /usr/share/nginx/html
