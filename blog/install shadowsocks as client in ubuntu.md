#Step 1: install shadowsocks

```
> sudo apt-get install python-pip
> sudo pip install shadowsocks
```

#Step 2: Create a Configuration File
```
> sudo vi /etc/shadowsocks.json
```
then:
```
{
    "server":"server-ip",
    "server_port":8000,
    "local_address": "127.0.0.1",
    "local_port":1080,
    "password":"your-password",
    "timeout":600,
    "method":"aes-256-cfb"
}
```
#Step 3: Run.
1. Run in terminal
    ```
    > sslocal -c /etc/shadowsocks.json
    ```
2. Run in background
    ```
    > sudo sslocal -c /etc/shadowsocks.json -d start
    ```

#Step 4: Debug
1. Commund not found
    add the directory of sslocal in to sudo path.
    ```
    > sudo visudo
    ```
    then add your sslocal directory in the end of "secure_path" line.
2. Can't connect to internet using firefox.
    ok, just using chrome instead.
3. Even using chrome can't connect to the internet.
    ```
    open: System Settings -> NetWork -> Network proxy
    add: 127.0.0.1, 1080 in "Socks Host" line.
    ```