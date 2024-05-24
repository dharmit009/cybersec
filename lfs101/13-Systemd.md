# Systemd

Systems with systemd start up faster than those with earlier init methods. This is largely because it replaces a serialized set of steps with aggressive parallelization techniques, which permits multiple services to be initiated simultaneously.

Complicated startup shell scripts are replaced with simpler configuration files, which enumerate what has to be done before a service is started, how to execute service startup, and what conditions the service should indicate have been accomplished when startup is finished. **One thing to note is that `/sbin/init` now just points to `/lib/systemd/systemd`; i.e. systemd takes over the init process**.

**Commands to start / stop / restart a service:**

$ sudo systemctl <start | stop | restart> <service name>.service
$ sudo systemctl start httpd.service

**Commands to enable or disable services:**

$ sudo systemctl <enable | disable> <service name>.service
$ sudo systemctl enable httpd.service

**Commands to view status of service:**

$ sudo systemctl status <service name>.service
$ sudo systemctl status httpd.service


