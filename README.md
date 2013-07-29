Redis Config/Init
====================

Redis init scripts and config files for running multiple instances for Magento.

These files were written for CentOS 6.3/4 and have been tested on RHEL as well. 

This is being used so we can create 3 instances for Magento Enterprise - sessions, object cache and full page cache. Each instance (obj, ses, and fpc) have their own init scrip and configuration file.


Installing
===================
Move files from init to /etc/init.d
Move files from conf to /etc/redis

Ensure the folders have been created for where we are storing the logs and data

Make the files executable and add to chkconfig so they start on reboot

sudo chmod 755 /etc/init.d/redis-obj
sudo chkconfig --add redis-obj
sudo chkconfig --level 345 redis-obj on

sudo chmod 755 /etc/init.d/redis-ses
sudo chkconfig --add redis-ses
sudo chkconfig --level 345 redis-ses on

sudo chmod 755 /etc/init.d/redis-fpc
sudo chkconfig --add redis-fpc
sudo chkconfig --level 345 redis-fpc on