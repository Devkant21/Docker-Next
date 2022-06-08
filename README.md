## Docker + Next

The codebase of this repository is dockerized.

## Steps :

- Create a NextJs application.
  ```
  npx create-next-app docker_next
  ```
- Setup a Dockerfile in the root directory

  - Contents of the Dockerfile :

    ```
    FROM node:current-alpine
    WORKDIR /app

    COPY package*.json ./
    RUN yarn install

    COPY . .
    CMD ["yarn", "dev"]
    ```

- Setup a .dockerignore in the root directory

  - Contents of the Dockerfile :

    ```
    # All files that are not required in our build
    Dockerfile
    .dockerignore
    .gitignore

    # Artifacts that'll be built during image creation
    node_modules
    ```

## Build the docker image :

    ```
    docker build -t next-image
    ```
