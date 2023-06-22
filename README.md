# STK_config
## Installation
Install dependencies:
```bash
sudo apt install wget git subversion make build-essential cmake pkg-config zlib1g-dev libcurl4-openssl-dev libssl-dev
```

Download the source code:
```
git clone https://github.com/supertuxkart/stk-code stk-code
```

Download assets:
```
svn co https://svn.code.sf.net/p/supertuxkart/code/stk-assets stk-assets
```

Create & enter the work directory for build process:
```
cd stk-code
mkdir cmake_build
cd cmake_build
```

Use this to build STK (You can add `-jX` to the make command to utilize X CPU cores)
```
cmake .. -DSERVER_ONLY=ON
make -j2
```

Change the binary's path to make it a command:
```
sudo mv /bin/supertuxkart /usr/bin/
```

Log in to SuperTuxKart Online:
```
supertuxkart --init-user --login="USERNAME" --password="PASSWORD"
```
Open the port:
```
sudo ufw allow 2759
```

Download server config:
```
git clone https://github.com/demorsick/STK_config.git
```

-------------------

## running the server
Start sthe server:
```
sudo nohup ./bin/supertuxkart --server-config=server.xml --network-console &
```
Add bots(10 is the number of bots):
```
sudo nohup supertuxkart --connect-now=127.0.0.1:2759 --network-ai=10 &
```
