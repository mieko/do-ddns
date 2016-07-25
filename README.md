# do-ddns

The script updates a Digitial Ocean DNS record with one given on the
command-line.  It makes no effort to *determine* your IP address, but is
useful in situations where you know it.

You'll need a DigitalOcean API key and configure the script in the header.

This was designed to run on a router with systems like [asus-wrt](https://github.com/RMerl/asuswrt-merlin).

The script depends on [JSON.sh](https://github.com/dominictarr/JSON.sh), and
will download a copy into the current directory (pinned to a known SHA) if it
doesn't exist.  If your deploy won't have write access, download it and give it
executable permissions in the same directory.
