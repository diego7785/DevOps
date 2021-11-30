FROM node:16-alpine
RUN apk add  --no-cache ffmpeg

ENV NODE_ENV=production
ENV GPU_TRANSCODING=FALSE

# Create app directory
WORKDIR .

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./

#RUN npx browserslist@latest --update-db
#RUN npm uninstall @babel/plugin-proposal-class-properties
#RUN npm install
#RUN npm install --save-dev @babel/plugin-proposal-class-properties
# If you are building your code for production
# RUN npm ci --only=production

# Bundle app source
COPY . .

RUN npm run build

EXPOSE 3001

CMD [ "npm", "run", "start" ]
