import test - file in parent directory 

```
cjs
 |- main/main.js - require("../sub/sub")
 |- sub/sub.js   - empty
esm-with-extensions
 |- main/main.mjs - import "../sub/sub.mjs"
 |- sub/sub.mjs   - empty
esm-without-extensions
 |- main/main.mjs - import "../sub/sub"
 |- sub/sub.mjs   - empty
```

```bash
$ node -v
v10.0.0
$ node ./cjs/main/main.js # success
$ node --experimental-modules ./esm-with-extensions/main/main.mjs # error ONLY ON WINDOWS
$ node --experimental-modules ./esm-without-extensions/main/main.mjs # success
```
