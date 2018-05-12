# Ideas and far future

## Near future

**TODO.** Collect ideas here

### Divide functionality into separate modules

For example, create two primary modules `fs` and `db`.

One secondary module `fs-meta`.

And then there will be modules that depend on `fs` or `db` module, or other user modules.

That's one of the reasons for using node.js and npm, but I hope I can do it in Kotlin.

### Note about `fs` and `db`

My first idea was that `fs` and `db` objects should share the same directory tree, but I realized that it can be painful to manage and keep them in sync, so dividing `fs` and `db` should be ok.

### `scheduler` module

Allows scheduled script executions.

For example, call scripts at path `/schedule/10min` every 10 minutes, at path `/schedule/1hour` every 1 hour etc.

### Execution queue

Show scripts pending for execution.

### Admin

Create admin account for adjusting settings, watching status.

### Module settings

Separate settings page for every module.

### `fs` module

I would like to have metadata assigned to every file stored in fs.

But that looks like it requires more complex implementation of fs, not just like storing files and just forwarding fs operations to the server system fs implementation.

### `db` module

#### Objects definition

BSON documents can include arbitary fields of arbitary types.

That is useful in a lot of cases, but it's possible to add strongly typed objects.

So the idea is to specify objects description and create types.

For example, an object describing `Box`:

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

Imagine a simple collection of objects.

That can also include indexes and other types of useful things.

So the idea is to create a virtual directory which is assigned to that collection.

For obvious reasons, that directory can't include subdirectories.

For example:

```
/
    dir1/
            boxes/      * This is a virtual directory, collection of boxes
                box1
                box2
                box3
                box4
```

So, this is the virtual directory `boxes`, which is a collection of 4 boxes.

It's also possible to execute standard MongoDB queries in that directory.

Also, there can be many other examples of virtual directories.

They can be either similar to collections or not.

You can imagine collections which disallow deleting documents from them.

#### Note about virtual directories

They are provided with modules. Module includes virtual directories definition and required logic.

Logic can be provided inside class that overrides fs functions.

For example:

```
class DbCollection {
    constructor(...) {}

    createDirectory(args) {
        throw NotAllowed()
    }

    list() {
        return this.collection.findAll()
            .map(...)
    }

    remove(...) {}

    // and so on
}
```

Nested structures are under consideration.

### Scrobbling

Add support of different scrobbling models.

From visited pages up to visited places.

### Visual

Implement beatiful visual representations of things on the client side.

Graphs, diagrams and so on.

## Can wait longer

### On the fly encryption

Or just encryption.

It depends more on the client side, but keeping the public key on server and using it for encrypting the uploaded files on the fly can also be done.

## Far far far future

I think it'd be cool to store metadata in blockchain (2018 - why not?)
