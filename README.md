# Odoo 15

The repository support run odoo 15 in docker whith traefik.

## How to run?

```bash

git clone https://github.com/raulchiclano/odoo-traefik.git

cd odoo-traefik

cp .env.sample .env

docker-compose -f docker-compose-traefik.yml up -d

docker exec -ti --user root odoo chown -R odoo:odoo /mnt/extra-addons/ var/lib/odoo/

sudo touch /etc/odoo/odoo.conf
sudo nano /etc/odoo/odoo.conf
  and add "
  [options]
  addons_path = /mnt/extra-addons
  data_dir = /var/lib/odoo

  "

```

## How to create custom module?

```bash
docker exec -ti odoo odoo scaffold /mnt/extra-addons/custom_module
```
