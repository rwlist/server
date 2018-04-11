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

### `fs` module

I would like to have metadata assigned to every file stored in fs.

But that looks like it requires more complex realization of fs, not just like storing files and just forwarding fs operations to the server system fs implementation.

### `db` module

#### Objects definition

BSON documents can include arbitary fields of arbitary types.

That is useful in a lot of cases, but it's possible to add strongly typed objects.

So the idea is to specify objects description and create types.

For example, object describing `Box`:

```
{
    _id: ObjectId,
    h: Double,
    w: Double,
    l: Double,
    objects: Long,
    created: Timestamp,
    ownerName: String
}
```

Types of fields are similar to [BSON](https://docs.mongodb.com/manual/reference/bson-types/).

#### Virtual directories

Imagine a simple collection with objects.

That can also include indexes and other types of useful things.

So the idea is to create virtual directory that is assigned to that collection.

For obvious reasons, that directory can't include subdirectories.

For example:

```
/
    dir1/
            boxes/      :that is a virtual directory, collection of boxes
                box1
                box2
                box3
                box4
```

So, here is virtual directory `boxes`, that is a collection of 4 boxes.

It's also possible to execute standard MongoDB queries in that directory.

Also, there can be many other examples of virtual directories.

They can be similar to collections, can be not.

You can imagine a collections which deny deleting documents from them.

## Can wait longer

### On the fly encryption

Or just encryption.

It depends more on the client side, but keeping the public key on server and using it for encrypting the uploaded files on the fly can also be done.

## Far far far future

I think it'd be cool to store metadata in blockchain (2018 - why not?)
