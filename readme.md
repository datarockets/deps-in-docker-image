Install the app `docker-compose up` and make sure it works on [localhost:3000](http://localhost:3000).


Install [morgan](https://github.com/expressjs/morgan)
```
docker-compose run --rm server npm install morgan
```
```
npm WARN app@1.0.0 No repository field.

+ morgan@1.10.0
added 4 packages from 2 contributors and audited 54 packages in 1.627s
found 0 vulnerabilities
```

Amend index.js to use it.

Run server:
```
docker-compose up
```

It won't be added to `node_modules`? 🤷‍♀️
```
Starting depsinimage_server_1 ... done
Attaching to depsinimage_server_1
server_1  | internal/modules/cjs/loader.js:1088
server_1  |   throw err;
server_1  |   ^
server_1  |
server_1  | Error: Cannot find module 'morgan'
server_1  | Require stack:
server_1  | - /app/index.js
server_1  |     at Function.Module._resolveFilename (internal/modules/cjs/loader.js:1085:15)
server_1  |     at Function.Module._load (internal/modules/cjs/loader.js:928:27)
server_1  |     at Module.require (internal/modules/cjs/loader.js:1145:19)
server_1  |     at require (internal/modules/cjs/helpers.js:75:18)
server_1  |     at Object.<anonymous> (/app/index.js:2:16)
server_1  |     at Module._compile (internal/modules/cjs/loader.js:1256:30)
server_1  |     at Object.Module._extensions..js (internal/modules/cjs/loader.js:1277:10)
server_1  |     at Module.load (internal/modules/cjs/loader.js:1105:32)
server_1  |     at Function.Module._load (internal/modules/cjs/loader.js:967:14)
server_1  |     at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:60:12) {
server_1  |   code: 'MODULE_NOT_FOUND',
server_1  |   requireStack: [ '/app/index.js' ]
server_1  | }
depsinimage_server_1 exited with code 1
```
