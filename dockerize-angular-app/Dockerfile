# first stage of building angular image
FROM node:slim as build
RUN mkdir -p /app
WORKDIR /app
COPY package.json /app/
RUN npm install
COPY . /app/
RUN npm run build --prod

# second stage
FROM nginx:alpine
COPY --from=build /app/dist/dockrize-app /usr/share/nginx/html
