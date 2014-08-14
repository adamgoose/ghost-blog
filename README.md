# Install on Laravel Forge

1. Disable nginx with `sudo update-rc.d -f nginx disable`
2. Create a new site for your blog, and install this Git Repository
3. Execute `npm install --production` in `/home/forge/{YOUR_GHOST_BLOG_SITE_NAME}`.
4. Reboot your server
5. Add a daenom for the root user that executes `npm start /home/forge/{YOUR_GHOST_BLOG_SITE_NAME} --production`
6. Update your deploy script to look like this:

        cd /home/forge/{YOUR_GHOST_BLOG_SITE_NAME}
        git pull origin master
        npm install --production
        forge daemon:restart {YOUR_DAEMON_ID}

7. Ta da!