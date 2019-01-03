# Traefik

Homepage: [https://traefik.io](https://traefik.io)

Traefik is used to provide external access to your Ansible-NAS box. Additionally, Traefik will automatically request and renew SSL certificates for you.

## Usage

Set `traefik_enabled: true` in your `group_vars/all.yml` file.

By default, Ansible-NAS is set up to use Let's Encrypt's "[staging](https://letsencrypt.org/docs/staging-environment/)" environment. This allows us to perform numerous test runs of the playbook without hitting Let's Encrypt production certificate [rate limits](https://letsencrypt.org/docs/rate-limits/).

Once you are happy with the results of the playbook, please delete the Traefik container, set `traefik_production: true` in your `group_vars/all.yml` file, and run your playbook again.

Traefik's web interface can be found at http://ansible_nas_host_or_ip:8083.

## Specific Configuration

You'll need to map port 80 and 443 from your router to your Ansible-NAS box. A quick search should reveal instruction for your model of router.