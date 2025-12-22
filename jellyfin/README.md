# Jellyfin

## Installation

1. Use sparse git clone to download jellyfin directory from services repo

```sh
git clone --filter=blob:none --sparse git@github.com:alamansky/services.git
cd services
git sparse-checkout add jellyfin
mv jellyfin ..
cd ..
rm -rf services
```

2. Create `jellyfin/volumes` directory and `jellyfin/.env` file

```sh
cd jellyfin
mkdir volumes
touch .env
```

3. Populate `.env` file with the following environment variables:  

- `PORT` - the port on which to serve the application

4. Start the container using docker compose

```sh
docker compose up -d
```

## Reference

Use a web browser to navigate to the application port on your host IP address. This should serve the login page to create an account.

To add media, move files into the `volumes` subdirectories according to content type.

Music files should have embedded metadata, which allows jellyfin to automatically discover album art, artist info etc.

## Further Reading

- https://github.com/jellyfin/jellyfin
- https://docs.linuxserver.io/images/docker-jellyfin/
