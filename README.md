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

| Application | Type | Download                                                                                                          | Notes |
| ----------- | ---- |-------------------------------------------------------------------------------------------------------------------| ----- |
| WordPress | Simple | [Click to Download](https://raw.githubusercontent.com/petehouston/nginx-conf-files/dev/conf/wordpress_simple.conf) | - |
| WordPress | Advanced | [Click to Download](https://raw.githubusercontent.com/petehouston/nginx-conf-files/dev/conf/wordpress_advanced.conf) | - |
| Laravel | Simple | [Click to Download](https://raw.githubusercontent.com/petehouston/nginx-conf-files/dev/conf/laravel_simple.conf)  | - |
| Laravel | Advanced | [Click to Download](https://raw.githubusercontent.com/petehouston/nginx-conf-files/dev/conf/laravel_advanced.conf) | - |
| Drupal | Generic | [Click to Download](https://raw.githubusercontent.com/petehouston/nginx-conf-files/dev/conf/drupal.conf)          | applied to Drupal v8+ |
| Symfony 6 | Simple | [Click to Download](https://raw.githubusercontent.com/petehouston/nginx-conf-files/dev/conf/symfony_6_simple.conf) | [Reference](https://symfony.com/doc/current/setup/web_server_configuration.html#nginx) |

## Leverage Let's Encrypt SSL

Once you add the config to nginx, you can add Let's Encrypt config to site config via `certbot`. 

```shell
$ sudo certbot --nginx -d example.com -d www.example.com
```

All necessary config fields for SSL will be added automatically, so you don't have to do anything at this point.