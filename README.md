# Vesta-Nginx-Statamic ( v2 )

A working Nginx config for usage in a VestaCP Install with a few tweaks.

## CentOS 7 + VestaCP + NGINX + PHP-FPM + ^ PHP 7

VestaCP fiddles with the confs a bit and it took me as tad to figure out a working nginx.conf for Statamic.

Tested on a VPSDIME VPS

## Disclaimer

Backups are next to nobility. Before fiddling with your conf be sure to backup the defaults. I will not be held responsible for support or damage should you trash something.
Use at your own risk!

## Want to take VestaCP + Nginx + PHP-FPM to run on PHP 7

You will need PHP7 or at least a PHP Upgrade from the default to run Statamic. So why not go the whole hog!

Once your server is spooled up and running VestaCP ( Remove anything you wont need, bloated servers suck )

There are plenty repos which will serve you PHP7 Common ( pretty much all you will need ) I use these:

`rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm`
`rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm`

### Plugin Replace

`yum install yum-plugin-replace`

Will install one of my favorite fiddle around tools.

### Release the hounds

`yum replace php-common --replace-with=php70w-common`

Replace that shite & you are done!

### Initiators

Both Nginx & PHP-FPM will need to be set to start on reboot after this upgrade. ( `chkconfig SERVICE on` or `systemctl enable SERVICE.service` )

Note: its a game of Russian roulette on server if init.d scripts will be added on yum install or plugin replace, so you may want to do that to pretty up the responses.
If I have time I will add scripts, other wise google is your friend.
