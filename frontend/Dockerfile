# Stage 1: Build the React app
FROM node:20 as build 


WORKDIR /src

COPY package.json package-lock.json ./
RUN npm install


COPY . ./
RUN npm run build


# Stage 2: Serve th React app
FROM nginx:alpine

COPY --from=build /dist /usr/share/nginx/html
EXPOSE 80

CMD [ "nginx", "-g", "daemon off;" ]
