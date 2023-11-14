# How to start?	

step1: clone me =)

```
git clone https://repo.arnika.ai/a_sharifianzadeh/capital_market_docs.git
```

step2:

Install all requirements.

```
pip install -r requirements.txt
```
step3:
Install drawio native on linux. You can do that in 2 way:
1- Download deb file and install it.
2- Install snap package manager and install drawio from snap store.(easier way)

1- Download deb file and install it.
first install dependencies:
```shell
sudo apt update
sudo apt upgrade
sudo apt install wget apt-transport-https gnupg2


```

After that download and install drawio:
```shell
curl -s https://api.github.com/repos/jgraph/drawio-desktop/releases/latest | grep browser_download_url | grep '\.deb' | cut -d '"' -f 4 | wget -i -
sudo apt -f install ./drawio-amd64-*.deb
```

or

2- Install snap package manager and install drawio from snap store.
you can install drawio with snapd:
```shell
sudo apt install snapd
```
and install from snapd:
```shell
sudo snap install core
sudo snap install drawio
```

step4:

Run this:

```
mkdocs serve
```
Now enjoy it =)


