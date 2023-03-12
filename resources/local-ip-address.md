# If you want to view your locally hosted site on your phone (instead of using the emulator)

1. First: make sure Live Server is running.

2. On your machine

- [On a Mac:](https://blog.pcrisk.com/mac/12377-how-to-find-out-your-ip-address-on-mac)

  - Open terminal
  - type `ipconfig getifaddr en0`

- [On Windows 10:](https://idoc.vsb.cz/xwiki/bin/view/tuonet/sit-nastaveni/ip-adresa/ip-win10-cmd/?xpage=print&language=en)
  - Open command prompt
  - Type `ipconfig /all` and press Enter.
  - Find your Ethernet adapter Ethernet, locate row `IPv6 Address`

3. Type the ip address into your mobile device url bar, followed by the port Live Server is running

4. [📺 - View Development on Your Phone](https://youtu.be/WfpY-g9bQM4)
