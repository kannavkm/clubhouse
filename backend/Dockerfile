FROM node:14

# Create app directory
WORKDIR /app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./

ENV NODE_ENV production

RUN npm install
# If you are building your code for production
# RUN npm ci --only=production

RUN addgroup -g 1001 -S nodejs
RUN adduser -S nodejs -u 1001

COPY --chown=nextjs:nodejs . .

USER nodejs

EXPOSE 8080

CMD [ "node", "app.js" ]
