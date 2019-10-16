# Fix-E-Could-not-get-lock-var-lib-dpkg-lock-Error-in-Ubuntu-Quick-Tip-
Fix ‘E: Could not get lock /var/lib/dpkg/lock’ Error in Ubuntu [Quick Tip]
Method 1:
ps aux | grep -i apt
sudo kill -9 <process id
sudo killall apt apt-get


Method 2:
lsof /var/lib/dpkg/lock
lsof /var/lib/apt/lists/lock
lsof /var/cache/apt/archives/lock

sudo kill -9 PID

sudo rm /var/lib/apt/lists/lock
sudo rm /var/cache/apt/archives/lock
sudo rm /var/lib/dpkg/lock
sudo dpkg --configure -a

lsof /var/lib/dpkg/lock-frontend
sudo kill -9 PID
sudo rm /var/lib/dpkg/lock-frontend
sudo dpkg --configure -a
