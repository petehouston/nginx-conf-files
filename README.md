# nginx-conf-files

Some useful nginx config files for sites.

## Usage

1. Copy the appropriate config file and save into nginx site config directory, usually located at `/etc/nginx/sites-available`, and name it like domain name as a good practice.
2. Edit the config file to satisfy your requirements, then save.
3. Symbol link to `/etc/nginx/sites-enabled/`.
4. Restart nginx service

Those steps can be illustrated as follow commands:

```shell
$ sudo vi /etc/nginx/sites-available/example.com

-- edit file then save

$ sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/
$ sudo nginx -t
$ sudo systemctl reload nginx
```

## Config file list

| Application | Type | Download | Notes |
| ----------- | ---- | -------- | ----- |
| WordPress | Simple | - | - |
| WordPress | Advanced | - | - |
| Laravel | Simple | - | - |
| Laravel | Advanced | - | - |
| Drupal | Generic | - | applied to Drupal v8+ |

