# Ideas and far future

## Near future

**TODO.** Collect ideas here

### Divide functionality into separate modules

For example, create two main modules `fs` and `db`.

One semi-main module `fs-meta`.

And then there will be modules that depend on `fs` or `db` module, or other user modules.

That's one of the reasons for using node.js and npm, but I hope I can do it in Kotlin.

### Note about `fs` and `db`

My first idea was that `fs` and `db` objects should share the same directory tree, but I realized that it can be painful to manage and keep them in sync, so dividing `fs` and `db` should be ok.

### `scheduler` module

Allow scheduled script executions.

For example, call scripts at path `/schedule/10min` every 10 minutes, at path `/schedule/1hour` every 1 hour etc.

### Execution queue

Show scripts pending for execution.

### Admin

Create admin account for adjusting settings, watching status.

### Module settings

Separate settings page for every module.

## Can wait longer

### On the fly encryption

Or just encryption.

It depends more on the client side, but keeping the public key on server and using it for encrypting the uploaded files on the fly can also be done.

## Far far far future

I think it'd be cool to store metadata in blockchain (2018 - why not?)
