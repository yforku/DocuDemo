[&#x213C;](#)<br id="idx00">
# Install Docusarus
* [README](README.md)
* [Introduction](#idx01)
* [GitHub and SSH](#idx02)
* [Cloning GitHub Repo](#idx03)
* [Installing Docusaurus](#idx04)
* [Local Test](#idx05)
* [GitHub Page Deployment](#idx06)


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

* You are not cbkadal! You should replace GIT_USER, ORG, and REPO with your own.
  * GIT_USER: "cbkadal"
  * ORG:  "yforku"
  * REPO: "DocuDemo"
  * LINK: <https://github.com/yforku/DocuDemo/>

```
#!/bin/bash
echo You are not cbkadal! You should replace GIT_USER, ORG, and REPO with your own.
sleep 2
REPO="DocuDemo"
GIT_USER="cbkadal"
ORG="yforku"
USE_SSH="true"
LINK="$ORG/${REPO}.git"
echo The GIT LINK IS git@github.com:$LINK

```

* Cloning

```
#!/bin/bash
mkdir -vp $HOME/git/
[ -d $HOME/git/ ] || { echo "ERROR: no git directory!"; exit 1; }
cd $HOME/git/
git clone git@github.com:$LINK
[ -d $HOME/git/$REPO/ ] || { echo "ERROR: no $REPO repo!"; exit 1; }
cd $HOME/git/$REPO/
git status
ls -aF

```

[&#x213C;](#idx00)<br id="idx04">
## Installing Docusaurus
* You may replace "REPO" with your own repo.

```
#!/bin/bash
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
cd $HOME/git/$REPO/Docusaurus/
npm run start -- --host 0.0.0.0

```

* NAT from port 3000 to port 5001
* At your host, use 
  * <http://localhost:5001/>


[&#x213C;](#idx00)<br id="idx06">
## GitHub Page Deployment

* E.g., for deploying <https://yforku.github.io/DocuDemo/>, modify the following in file "docusaurus.config.js": 

```
  title: 'DocuDemo',                // Or else
  tagline: 'This is the Way!',      // Or else
  favicon: 'img/favicon.ico',       // Or else
  url: 'https://yforku.github.io',  // Or else
  baseUrl: '/DocuDemo/',            // Or else
  organizationName: 'yforku',       // (Usually your GitHub org/user name)
  projectName: 'DocuDemo',          // (Usually your repo name)
  trailingSlash: true,              // "true/" or "false"

```

* Deploy yarn

```
#!/bin/bash
[ -d $HOME/git/$REPO/Docusaurus/ ] || { echo "ERROR: no git directory!"; exit 1; }
cd $HOME/git/$REPO/Docusaurus/
yarn deploy

```


[&#x213C;](#idx00)<br id="idxZZ">
## This is the Way!

```
#### REV02: Sat 06 May 2023 22:00
#### REV01: Fri 05 May 2023 20:00
#### START: Fri 05 May 2023 15:00
```
