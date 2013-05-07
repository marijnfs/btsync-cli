btsync-cli
============

Console Application for BitTorrent SyncApp WebUI written in Go
Alpha version. Tested against 1.0.116.

Features
------
  * add folder to sync folders (with empty or predefined secret)
  * remove folder from sync folders
  * list all sync folders
  * generate secret (with readonly secret)

Example Usage
------

    Usage of btsync-cli.exe:
      -a="":              path to add for index
      -d="":              path to delete from index
      -g=false:           get new secret
      -host="127.0.0.1":  btsync webui hostname
      -l=false:           list folders
      -p="admin":         password
      -port="8888":       btsync webui port
      -s="":              secret, if empty will be autogenerated
      -u="admin":         username
      -v=false:           verbose mode on


Known Issues
------
  * delete folder always returns true
  * russian utf-8 names are in win-1252 encoding (via -l)


How-to build on Synology DS210j
------
    cd ~btsync-cli
    export GOPATH=`pwd`
    export GOARM=5
    /opt/go/bin/go build src/btsync-cli.go
    ./btsync-cli -h