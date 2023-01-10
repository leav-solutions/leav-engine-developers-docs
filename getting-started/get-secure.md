# 🛡 Get secure

Enabling HTTPS access is highly recommended when you'll run LEAV-Engine on a public domain.

Here are the few modifications on the base docker-compose file to do so:

* On the `core` service, add these labels:

```
- traefik.http.routers.core.rule=Host(`<your public domain>`)
- traefik.http.routers.core.entrypoints=web,websecure
- traefik.http.routers.core.tls.certresolver=letsencrypt
```

* On the `traefik` service, add these labels:

```
- "--entrypoints.websecure.address=:443"
- "--entrypoints.web.http.redirections.entrypoint.to=websecure"
- "--entrypoints.web.http.redirections.entrypoint.scheme=https"
- "--certificatesresolvers.letsencrypt.leav_engine.email=contact@leav-solutions.com"
- "--certificatesresolvers.letsencrypt.leav_engine.storage=/letsencrypt/leav_engine.json"
- "--certificatesresolvers.letsencrypt.leav_engine.tlschallenge=true"
```

* On the `traefik` service, open the port 443:

```
- "443:443"
```

* On the `traefik` service, add a volume to store the certificates:

```
- lets_encrypt_cert:/letsencrypt
```

* Add the certificates volume to the volumes section:

```
lets_encrypt_cert:
    driver: local
```

* Don't forget to use secure protocols in public URLs:

```
SERVER_PUBLIC_URL: https://<your public domain>
SERVER_WS_URL: wss://<your public domain>
```
