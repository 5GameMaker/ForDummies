#http #tools #protocol
[[Git]] over [[HTTP]] is the most used way to clone a repo, but when it comes to docs - they are pretty much nonexistent. So here are the only docs on this you'll ever see.

Git always sends a `User-Agent: git/<version>` header which can be used to distinguish between git and browser.

These docs were constructed during the creation of [[bgit]].
# Dumb server
Dumb server protocol is the easiest one to implement, as such [[bgit]] supports it.

Every request should include `Content-Type: text/plain;charset=utf-8` header.
Every request is sent to `http://<server>/<path>.git/...`.
## Fetching refs
We begin with a request to `/info/refs`. The server must respond with a list of refs:
```bindef
"200 OK"\r\n
\r\n
{hash}\t{ref}\r\n
{hash}\t{ref}\r\n
\n
```
# See also
1. [[Bare Repository]]
# Sources
1. https://www.git-scm.com/docs/http-protocol