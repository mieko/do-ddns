# do-ddns

The script updates a Digitial Ocean DNS record with one given on the
command-line.  It makes no effort to *determine* your IP address, but is
useful in situations where you know it.

You'll need a DigitalOcean API key and configure the script in the header.

This was designed to run on a router with systems like [asuswrt-merlin](https://github.com/RMerl/asuswrt-merlin).

The script depends on [JSON.sh](https://github.com/dominictarr/JSON.sh), and
will download a copy into the current directory (pinned to a known SHA) if it
doesn't exist.  If your deploy won't have write access, download it and give it
executable permissions in the same directory.

## Example Usage
 ### Basic
 ```bash
./do-dns 203.0.113.25
```
 ### Actual Use: ASUS Router w/ [Padavan Firmware](https://bitbucket.org/padavan/rt-n56u)
 ```bash
./do-ddns $(ifconfig eth2.2 | grep -Eo 'inet (addr:)?([0-9]*\.){3}[0-9]*' | grep -Eo '([0-9]*\.){3}[0-9]*' | grep -v '127.0.0.1')
```
 This command uses the IP address of the device's eth2.2 interface as do-ddns' IP address parameter.
