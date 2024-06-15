# Use an official Node.js runtime as the base image
FROM node:lts-alpine AS build

# Set the working directory inside the container
WORKDIR /usr/src/app
# Copy package.json and package-lock.json to the working directory
COPY /FFXIV_Trading_UI/package.json .
COPY /FFXIV_Trading_UI/package-lock.json .
# Install project dependencies
RUN npm install
# Copy the entire project to the working directory
COPY ./FFXIV_Trading_UI .
# Build the Angular app

RUN npm run build

FROM build as dev-envs
CMD ["npm", "run", "start"]
