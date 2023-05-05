[&#x213C;](#)<br id="idx00">
# Install Docusarus
* [README](README.md)
* [Introduction](#idx01)
* [GitHub and SSH](#idx02)
* [Cloning GitHub Repo](#idx03)
* [Installing Docusaurus](#idx04)
* [Local Test](#idx05)


[&#x213C;](#idx00)<br id="idx01">
## Introduction

This part is not included in the OVA file because it contains SSH KEYS and GitHub account information. This part will use the user account "cbkadal" as an example. Remember, you are not "cbkadal," so you should replace "cbkadal" with your account. 
Again, you are not "cbkadal," so you should replace "cbkadal" with your account.

[&#x213C;](#idx00)<br id="idx02">
## GitHub and SSH
* In this example, we will use the GitHub account "cbkadal" and repo <https://github.com/yforku/DocuDemo/>. You should replace it with your own. See also [README](README.md#idx03).
* Generating a GnuPG KEY PAIR. See <https://osp4diss.vlsm.org/osp-110.html>.
* Put a Public Key at GitHub.com. See <https://osp4diss.vlsm.org/osp-111.html>.
* Setting .gitconfig. See <https://osp4diss.vlsm.org/osp-112.html>.

[&#x213C;](#idx00)<br id="idx03">
## Cloning GitHub Repo
* In this example, we will use the GitHub account "cbkadal" and repo <https://github.com/yforku/DocuDemo/>. You should replace it with your own. See also [README](README.md#idx03).
* Test your SSH connection to GitHub.

```
#!/bin/bash
ssh -T git@github.com

```

* Cloning
  * USER: "cbkadal"
  * ORG:  "yforku"
  * REPO: "DocuDemo"
  * LINK: <https://github.com/yforku/DocuDemo/>

```
#!/bin/bash
echo You are not cbkadal! You should replace USER, ORG, and REPO with your own.
sleep 2
USER="cbkadal"
ORG="yforku"
REPO="DocuDemo"
LINK="$ORG/${REPO}.git"
mkdir -vp $HOME/git/
[ -d $HOME/git/ ] || { echo "ERROR: no git directory!"; exit 1; }
cd $HOME/git/
git clone git@github.com:$LINK
[ -d $REPO/ ] || { echo "ERROR: no $REPO repo!"; exit 1; }
cd $REPO/
git status
ls -aF

```

[&#x213C;](#idx00)<br id="idx04">
## Installing Docusaurus
* You may replace "REPO" with your own repo.

```
#!/bin/bash
REPO="DocuDemo"
echo "Using repo $REPO/"
sleep 2
[ -d $HOME/git/$REPO/ ] || { echo "ERROR: no git directory!"; exit 1; }
cd $HOME/git/$REPO/
echo "Installing Docusaurus..."
npm init docusaurus@latest Docusaurus classic
cd $HOME/git/$REPO/Docusaurus/
ls -al

```

[&#x213C;](#idx00)<br id="idx05">
## Local Test
* Run

```
#!/bin/bash
REPO="DocuDemo"
cd $HOME/git/$REPO/Docusaurus/
npm run start -- --host 0.0.0.0

```

* NAT from port 3000 to port 5001
* At your host, use 
  * <http://localhost:5001/>



[&#x213C;](#idx00)<br id="idxZZ">
## This is the Way!

```
#### REV01: Fri 05 May 2023 17:00
#### START: Fri 05 May 2023 15:00
```
