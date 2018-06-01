# Google Cloud Pub/Sub for Docker

This repo contains a _ridiculously small_ Docker image for the [Cloud Pub/Sub Emulator](https://cloud.google.com/pubsub/docs/emulator) for usage in development.

_Only use this image in development, do not use this in production!_

## Usage

1. With `docker-compose`:

   ```yaml
   ---
   version: '3.6'

   services:
     pubsub:
       image: adhawk/google-pubsub-emulator
       ports:
         - 8085:8085
   ```

2. Plain `docker` command:

   ```sh
   docker run -p 8085:8085 adhawk/google-pubsub-emulator
   ```

3. Make sure to set these environment variables in your app that requires the
   pubsub service

   ```sh
   export PUBSUB_EMULATOR_HOST=localhost:8085
   ```
