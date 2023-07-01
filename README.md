![image](https://github.com/MeekOnGithub/LGTV-WEBOS-REMOTE-CONTROL/assets/89902968/1303e111-0683-43db-add1-49f21c3a438d)



> A hacky implementation of webOS remote control API on an app.
(Fork from [/throwaway96](https://github.com/throwaway96/webos-ssap-web))

Still not done !

**What this fork do ?**
------------

- Make the web client, work in an app
- Make it more beautiful and user-friendly
- And add some Qol functions


How it works
------------

By default a server implementing SSAP on webOS prevents web origins from
accessing its websocket. However there are exceptions to allow communication
from chrome extensions *and `file://` origins*. Both `file://` and `data:`
origins present themselves to remote server as `Origin: null`. We use that to
allow http-based origin to communicate with SSAP server using a hidden iframe
with `src="data:..."` communicating back and forth with the main `http://`
frame. This is implemented in `wsproxy.js`.

Limitations
-----------

Currently this client can't be effectively used on `https://` origins due to
mixed content security policies. Alternatively, user can be requested to
manually approve self-signed certificate used for `wss://:3001` server exposed
by webOS.



Credits
-------

Remote UI by [simon_34545](https://github.com/Simon34545).

Original forked repository [/throwaway96](https://github.com/throwaway96/webos-ssap-web)
