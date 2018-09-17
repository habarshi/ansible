# Ansible scripts for deploying **Habarshi** server

## Supported platforms

- Ubuntu 16.04 LTS (Xenial)
- Debian 8 (Jessie)
- Debian 9 (Stretch)

## Playbook variables

- **`habarshi_path`**: `"/opt/habarshi"` -  Habarshi server binaries and config files destination path
- **`habarshi_keys_path`**: `"{{habarshi_path}}/keys"` - SSL certificate and key file destination
- **`habarshi_domain`**: `"habarshi.local"` - Habarshi server domain name
- **`habarshi_subnet`**: `"192.168.8.0/24"` - Docker containers virtual network subnet
- **`habarshi_gateway`**: `"192.168.8.1"` - Docker containers virtual network gateway
- **`habarshi_db_ip`**: `"192.168.8.2"` - Habarshi database server local network address
- **`habarshi_ip`**: `"192.168.8.4"` - Habarshi server local network address
- **`habarshi_db_user`**: `"root"` - Habarshi database user
- **`habarshi_db_pass`**: `"root"` - Habarshi database user password
- **`habarshi_db_name`**: `"habarshi"` - Habarshi database name

## Step-by-step
1. Register your personal *HABARSHI* subdomain [https://panel.habarshi.com/](https://panel.habarshi.com/)  
2. Set `habarshi_domain` parameter to actual value, for example, if your domain = `my_domain.habarshi.com`, set `habarshi_domain: "my_domain.habarshi.com"`
3. Install any client ([https://panel.habarshi.com/home](https://panel.habarshi.com/home)) and login as `<login>@my_domain`

## Go to admin page (in Browser)
  Default admin: *root*
  Default admin password: *asisaka* - you should change it to more strong password value

## Examples:
  - Install on **localhost**: `sudo ansible-pull -e habarshi_domain=<subdomain>.habarshi.com -e habarshi_db_pass=<your db password> -U https://github.com/habarshi/ansible.git localhost.yml`

  - Install on remote host, see **example.yml** [https://github.com/habarshi/ansible/blob/master/example.yml](https://github.com/habarshi/ansible/blob/master/example.yml "example.yml") playbook (Type: `ansible-playbook example.yml`)
  - OR Navigate to example page [https://github.com/habarshi/ansible/tree/master/example](https://github.com/habarshi/ansible/tree/master/example) and up virtual machine 




## SSL certificates

 Place your SSL certificate and private key file to `habarshi_keys_path` directory:

- habarshi.crt
- habarshi.key

 if certificate `habarshi.crt` file will not be found, self-signed crtificates will be generated