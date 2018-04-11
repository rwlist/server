# Stage 1. MVP

## Development stack

At first I thought Node.js with Express.js is a good option (and I still think it's not bad) but I decided to use Kotlin as Kotlin can give **fun** and **joy**.

As it will be Kotlin, there will be some Java/Kotlin frameworks for web. I want to use reactive ones just because.

_Look at [this beautiful site](https://www.kotlinresources.com/) with Kotlin libraries._

Kotlin candidates for now:
- https://www.kotlinresources.com/library/ktor/
- https://www.kotlinresources.com/library/vertx-lang-kotlin/
- https://www.kotlinresources.com/library/hexagon/
- https://www.kotlinresources.com/library/kara/

_Btw, I liked Play Framework very much recently, but it is written in Scala, so I'm afraid it can't be used here._

It's the description of MVP, so it's possible to try several options for now.

## Basics

I see it all as the SPA using server API's, so the front-end framework also needs to be chosen, but I feel like it's far less important during the MVP stage.

For the MVP stage there should be several API endpoints (which maybe can be accessed via Swagger)

**TODO.** Use Swagger to get SWAG

## Auth

I don't know a lot about SPA and I think I should do a research about authentication in those apps. It's interesting, can I use plain old cookies for that?

Suggestion about using [JWT](https://auth0.com/docs/security/store-tokens)

## `fs` module

Create a directory for every user and store all files in that directory.

It should support the following functions:

- `listDirectory(path: String)`
- `createDirectory(path: String)`
- `downloadFile(path: String)`
- `uploadFile(path: String, stream: ByteStream)`
- `deleteOne(path: String)`
- `recursiveDelete(path: String)` (ask for confirmation as an option)

**TODO.** Add more functions, `move` at least.

`fs` is just a module that allows user to store files in separate directory directly on disk. So `fs` module provides basic functions as every fs do.

Check note about metadata on [ideas page](./ideas.md). Meta is useful and that's what I want to, but it shouldn't be implemented at this stage.

Basically, fs should be used only for blobs.

## `db` module

`db` is very similar to `fs`, but stores BSON documents in MongoDB.

It's also allows advanced structures like virtual directories, read more on [ideas page.](./ideas.md)

Add/delete directory, add/delete/edit document should be enough for the MVP.

## Development organization

GitHub has projects, I definitely should give them a try.

Markdown files are good for now, aren't they?
