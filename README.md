# foxglove-package-builder
Easily build foxglove packages dockerized.

 * Put this Dockerfile in your foxglove package workspace, next to your package.json file.
 * Build this docker image:
    `docker build -t foxglove-package-builder .`
 * Finally run the image to build your app:
    `docker run --rm -v "$(pwd):/app" -w /app foxglove-package-builder`
 * If the build succeeds, a .foxe file should appear in your workspace folder

Since this Docker-image installs your dependencies once, builds will iterate fast. However:
 * If you update your dependencies.json, you should rebuild the docker image
 * If you have multiple foxglove package workspaces, you might want to rename your docker image to keep separate projects apart
