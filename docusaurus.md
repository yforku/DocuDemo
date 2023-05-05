# Install Docusarus
* [README](README.md)
* [Introduction](#idx01)
* [GitHub and SSH](#idx02)


[&#x213C;](#)<br id="idx01">
## Introduction

This part is not included in the OVA file because it contains SSH KEYS and GitHub account information. This part will use the user account "cbkadal" as an example. Remember, you are not "cbkadal," so you should replace "cbkadal" with your account. 
Again, you are not "cbkadal," so you should replace "cbkadal" with your account.

[&#x213C;](#)<br id="idx02">
## GitHub and SSH
* In this example, we will use the GitHub account "cbkadal" and repo <https://github.com/yforku/DocuDemo/>.  
  You should replace it with your own. See also [README](README.md#idx03).
* Generating a GnuPG KEY PAIR. See <https://osp4diss.vlsm.org/W02-03.html>.
* Put a Public Key at GitHub.com. See <https://osp4diss.vlsm.org/osp-111.html>.
* Setting .gitconfig. See <https://osp4diss.vlsm.org/osp-112.html>.

[&#x213C;](#)<br id="idx03">
## Cloning GitHub Repo
* In this example, we will use the GitHub account "cbkadal" and repo <https://github.com/yforku/DocuDemo/>.
  You should replace it with your own. See also [README](README.md#idx03).
* Test your SSH connection to GitHub.

```
ssh -T git@github.com

```

* Cloning
  * USER: "cbkadal"
  * ORG:  "yforku"
  * REPO: "DocuDemo"
  * LINK: <https://github.com/yforku/DocuDemo/>

```
echo You are not cbkadal! You should replace USER, ORG, and REPO with your own.
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



[&#x213C;](#)<br id="idxZZ">
## This is the Way!

```
#### REV01: Fri 05 May 2023 16:00
#### START: Fri 05 May 2023 15:00
```
