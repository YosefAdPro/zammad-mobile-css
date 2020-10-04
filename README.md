# zammad-mobile-css
CSS modification for mobile devices (tested on Zammad version 3.5)

1. Create /opt/zammad/public/assets/custom-mobile.css and paste the mobile.css.
2. Modify /etc/nginx/sites-enabled/zammad.conf and add the following under location / section:

``sub_filter '</head>' '<link rel="stylesheet" href="/assets/custom-mobile.css"><meta name="apple-mobile-web-app-capable" content="yes"></head>';``

``sub_filter '<meta name="viewport" content="width=1024">' '<meta name="viewport" content="width=device-width, initial-scale=1.0">';``

``sub_filter_once on;``

3. Test NGINX configuration to make sure you didn’t make any typos:
``nginx -t``

4. Reload NGINX configuration
``nginx -s reload``

Source: https://community.zammad.org/t/css-modification-for-mobile/3941/7
