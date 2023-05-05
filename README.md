# DocuDemo

## OVA 
* Source: DOCU-2304-02.ova (Debian 11.7)
* Ref:
  * Debian ISO <https://doit.vlsm.org/012.html>
  * Preparation <https://doit.vlsm.org/013.html>
  * Instalation <https://doit.vlsm.org/014.html>

## Github
* URL: <https://github.com/yforku/>
* New Repo: [DocuDemo](https://github.com/yforku/DocuDemo/), Public, README, .gitignore:Node, MIT License, master branch

## Debian 11 sources.list (root)
* Ref:
  * sources.list <https://osp4diss.vlsm.org/osp-102.html>

```
[ -f /etc/apt/sources.list ] && mv /etc/apt/sources.list /etc/apt/sources.list.zold
cat > /etc/apt/sources.list << EOF
deb https://deb.debian.org/debian/  bullseye           main contrib non-free
deb https://security.debian.org/    bullseye-security  main contrib non-free
deb https://deb.debian.org/debian/  bullseye-updates   main contrib non-free
deb https://deb.debian.org/debian/  bullseye-backports main contrib non-free
EOF
apt-get update && apt-get upgrade -y

```

## Debian Package (root)

```
export DEBS="
aptitude
git
sudo
vim
"
date;
time apt-get install $DEBS -y
[ -d /etc/sudoers.d/ ] && echo "cbkadal    ALL=(ALL:ALL) ALL" > /etc/sudoers.d/cbkadal
time (aptitude update&&echo " =1= "&&aptitude safe-upgrade -y&&echo " =2= "&&aptitude autoclean -y;)

```



## This is the Way!
