Although [NodeJS](https://nodejs.org) and it's proprietary package manager, **NPM**, have come on a lot in recent times, versioning can still be a mine-field, when setup projects on different systems and environments.

With the release of version 3.x, **Node** has changed it's approach to some degree, by flattening the endless, recursively nested node_module folders, much to the relief of Windows users.

This goes some way, to mitigating the versioning issues, but the most fundimental action, you need to undertake, is locking down the versions of **Node** and **NPM**, that your prject requires. 

**EcmaScript 2015 (ES6)** `let` statements for example, just won't work under an incorrect version of **Node**, but you're not going to get a warning to that affect either! 

We can ensure that Node alert us to these issues though, fairly easily.

Package.json Engines
--------------------

Adding an `Engines` node to your package.json, ensures that you have the specified versions installed.  Well, when I say 'ensures', it will spit out warnings if the versions don't match.

For example, to specify the version of **node** that your stuff works on:

```language-json
{
    "engines": {
        "node: ">=0.10.3 <0.12"
    }
}
```

As per Npm's [documentation](https://docs.npmjs.com/files/package.json): 

> If you specify an "engines" field, then npm will require that "node" be somewhere on that list. If "engines" is omitted, then npm will just assume that it works on node.

Suffice to say, a fairly trivial addition, but an important one, when working across large teams, on different environments.