# Misc Linux/Unix Notes

### Some of My Favourite Things
* screen, byobu, tmux - terminal session managers 

* iftop - terminal interface monitor

* iptraf - network monitoring

* htop, btop - like top but more

* iotop - top for IO

* nagios - Monitoring

* iRedMail - all in one webmail solution

### systemd
* Rescue shell command line options to the kernel to pass to systemd 
   `systemd.unit=rescue.target` 

* or  
   `systemd.unit=emergency.target`  
   followed by:  
   `# mount -o remount,rw /`  
...to mount the filesystem read/write 

* Additionally,  
   `systemd.debug-shell=1`  
Opens a shell on tty9 very early in the boot process

### CentOS
* Activate epel repo in CentOS 6  
  `# yum install http://download.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm`
