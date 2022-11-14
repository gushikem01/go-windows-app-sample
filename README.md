## develop golang desktop application on WSL2

* Install Xlaunch in you PC

<https://dev.classmethod.jp/articles/wsl-x-window/>

* Add dependency to your project

```bash
go install -x -v github.com/go-delve/delve/cmd/dlv@v1.7.1-0.20210804080032-f95340ae1bf9
sudo apt install -y libx11-dev libxcursor-dev libxrandr-dev libxinerama-dev libxi-dev libgl1-mesa-dev libxxf86vm-dev
export PKG_CONFIG_PATH=/usr/lib/x86_64-linux-gnu/pkgconfig
```

<https://blog.odaryo.com/2020/01/wsl2-xserver-export-display/>

* .vscode/launch.json

```json
  "env": {
        "DISPLAY": "(YOURIPADDRESS):0.0",
```

* export DISPLAY

```bash
export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0.0
```
