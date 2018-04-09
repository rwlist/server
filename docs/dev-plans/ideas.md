# Ideas and far future

## Near future

**TODO.** Collect ideas here

### Divide functionality into separate modules

For example, create two main modules `fs` and `db`.

One semi-main module `fs-meta`.

And then there will be modules that dependent on `fs` or `db` module, or other user modules.

That's one of the reason for using node.js and npm, but I hope I can do it in Kotlin.

### Note about `fs` and `db`

My first idea was that `fs` and `db` objects should share the same directory tree, but I realized that it can be painful to manage and keep in sync, so divinding `fs` and `db` should be ok.

### `scheduler` module

Allow schedule script executions.

For example, call scripts at path `/schedule/10min` every 10 minutes, at path `/schedule/1hour` every 1 hour etc.

### Execution queue

Show scripts pending for execution.

### Admin

Create admin account for adjusting settings, watching status.

### Module settings

Separate settings page for every module.

## Can wait longer

### On fly cipher

Or just cipher.

It depends more on client side, but keeping the public key on server and use it for encrypting uploaded files on fly can be also done.

## Far far far future

I think it'll be cool to store metadata in blockchain (2018 - why not?)