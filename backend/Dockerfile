FROM node:14-alpine
# This is required by Choreo to run the container as a non-root user.
RUN adduser \
    --disabled-password \
    --gecos "" \
    --uid 10014 \
    "choreo"
# Use the above created unprivileged user
USER 10014
WORKDIR /src/app
COPY package.json .
RUN npm i
COPY . .
EXPOSE 9000
CMD ["npm", "start"]
