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

## Deb Packages

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
