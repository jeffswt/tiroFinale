# tiroFinale
An <del>*INEFFICIENT*</del> (improved a lot in v2.7 and v4.0 update) and *INSECURE* (to be improved) Python HTTP(S) proxy

The client-side program (*tiro*) requires OpenSSL and Python 3.x, and supports at least Windows and Linux.

The server-side program (*Finale*) requires Python 3.x, and supports at least [heroku](http://heroku.com) and MS Azure Web App.

![logo](http://www.madoka-magica.com/special/img/present01/icon_mami.png)

## Efficiency

Not using tiroFinale proxy: *LOAD: 3.02s*

![direct](https://cloud.githubusercontent.com/assets/6646473/17058008/6a7b9da8-5050-11e6-86b3-e81065bd9cca.png)

Using tiroFinale proxy (v4.0.02) from localhost: *LOAD: 3.32s*

![with_tf](https://cloud.githubusercontent.com/assets/6646473/17058009/6a7bc846-5050-11e6-85f1-85e0b5c7f36e.png)

## Server (`finale`) Setup

1. Clone the repository, then `cd finale`
2. `python3 -m pip install -r requirements.txt`
3. `vi finale.py` and fill in your server's PASSWORD and PORT
4. `python3 ./finale.py`

## Client (`tiro`) Setup

**You might want Windows binaries for the client: [Releases](https://github.com/xmcp/tiroFinale/releases)**

1. Clone the repository, then `cd tiro`
2. `python3 -m pip install -r requirements.txt`
3. `vi const.py` and fill in your preferences
4. Add `ssl_stuff/tiroFinale_CA.ca.crt` to the OS/web-browser CAs as you want
5. `python3 ./tiro_proxy.py`

## Todo-List

- [x] Add <del>GUI</del> WebUI support for `tiro`
- [x] Fix the `Content-Length` related bug
- [x] Improve efficiency
- [x] Add `GFWList` support
- [x] Implement auto-detecting mechanism (`Jaô-Shingan™`) as a backup of `GFWList`
- [x] Use wildcard SSL certificate if possible
- [x] Proxy auto-configuration on Windows
- [ ] Restore original proxy after exit
- [ ] Concurrent certificate signing
- [ ] Improve security *(low priority)*

## Abandoned Todo Items

- [ ] <del>Network error handling and retransmission</del> *(deprecated due to the compatibility concern)*
- [ ] <del>Showing statistics</del> *(deprecated as it's not so useful and it will probably affect efficiency somehow)*

## Special thanks to:

- [senko/tornado-proxy](https://github.com/senko/tornado-proxy)
- [Leryan/python-simplecacher](https://github.com/Leryan/python-simplecacher)
- [Leryan/genssl](https://github.com/Leryan/genssl)
- [Mickyj's blog article](http://blogs.msmvps.com/mickyj/blog/2013/10/31/programmatically-alter-automatically-detect-settings-in-ie-through-vbs/)