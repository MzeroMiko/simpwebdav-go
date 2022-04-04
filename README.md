# simpwebdav-go
simp webdav server written in go support authentication

# Usage
```bash
Usage of ./wdav:
  -addr string
        listen address (default "[::]:6000")
  -auth
        enable auth
  -cert string
        cert file if use https (default "simp.cert")
  -def string
        default user setting, scope:prefix:modify (default ".:/:false")
  -key string
        key file if use https (default "simp.key")
  -tls
        enable https
  -user value
        add user config: --user "user:pass:prefix:scope:modify"
```
# Build
```bash
go env -w GOPROXY=https://goproxy.cn && go env -w GO111MODULE=auto && go build --ldflags '-w -s' wdav.go && upx wdav 
```

# Example
```bash
$dir/wdav --addr [::]:6001 --tls --auth -def .:/:false -user admin:admin:/media:/:true -user demo:demo:/media/Share:/share:false
```

