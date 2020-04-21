
one:
	apt remove xscreensaver

apt.list:
	echo 'deb http://security.debian.org/debian-security buster/updates main contrib non-free' > /etc/apt/side_sources.list
	echo 'deb http://deb.debian.org/debian buster main contrib non-free' >> /etc/apt/side_sources.list
	echo 'deb http://deb.debian.org/debian buster-updates main contrib non-free' >> /etc/apt/side_sources.list
	echo 'deb http://deb.debian.org/debian buster-backports main contrib non-free' >> /etc/apt/side_sources.list
	echo 'deb [arch=amd64] https://download.docker.com/linux/debian buster stable' >> /etc/apt/side_sources.list 

tools:
	apt remove xscreensaver
	apt install git mercurial medit chromium
	git config --global core.editor vi

node:
	echo 'fs.inotify.max_user_watches=524288' >> /etc/sysctl.d/local.conf

