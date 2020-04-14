FROM node:13.12.0 as builder

# set working directory
WORKDIR /app

# add app
COPY . /app

# install and cache app dependencies
COPY package.json /app/package.json
RUN npm install

# build app
RUN npm run build

FROM nginx:1.17.9
COPY --from=builder /app/dist/berich-web /srv/mysite


