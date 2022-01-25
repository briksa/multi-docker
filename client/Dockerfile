from node:16-alpine3.14 as builder
workdir '/app'
copy ./package.json ./
run npm install
copy . .
run npm run buld

from nginx
expose 3000
copy ./nginx/default.conf /etc/nginx/conf.d/default.conf
copy --from=builder /app/build /usr/share/nginx/html
