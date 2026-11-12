# Birdsong (https://github.com/dopeytree/birdsong) as a Home Assistant add-on.
FROM ghcr.io/dopeytree/birdsong:0.42

# The page asks BirdNET-Go for data at "/api/...", from the root of whatever
# serves it. Home Assistant shows add-ons under a path of their own
# (/api/hassio_ingress/<token>/), so the page's BirdNET-Go address defaults to
# "." here instead: every request becomes relative to the page and reaches this
# container's proxy. The build stops if that line changes in a later version.
RUN apk add --no-cache jq \
 && sed -i 's|^  server: "",|  server: ".",|' /usr/share/nginx/html/index.html \
 && grep -q '^  server: ".",' /usr/share/nginx/html/index.html

COPY 04-ha-options.envsh /docker-entrypoint.d/
RUN chmod +x /docker-entrypoint.d/04-ha-options.envsh
