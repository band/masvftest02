### 2021-03-13

Testing Pete Kaminski's version of an obsidian-git fork that enables "commit -> pull -> push"

We had some warnings / errors on build:

```
> obsidian-git@1.5.0 build
> rollup --config rollup.config.js


main.ts → ....
(!) Unresolved dependencies
https://rollupjs.org/guide/en/#warning-treating-module-as-external-dependency
tty (imported by node_modules/debug/src/node.js, node_modules/supports-color/index.js,  tty?commonjs-external)
os (imported by node_modules/supports-color/index.js,  os?commonjs-external)
util (imported by node_modules/debug/src/node.js,  util?commonjs-external)
child_process (imported by node_modules/simple-git/src/lib/runners/git-executor-chain.js,  child_process?commonjs-external)
fs (imported by node_modules/@kwsites/file-exists/dist/src/index.js,  fs?commonjs-external)
created . in 7.9s
```

Note: now we are in the new software using business. How can we keep the end user instructions simple?

- rolled up the source code and git submodule stuff into a "gitCloset" directory
 - but maybe not soon enough; so we will see what kind of mess has been made


this does not seem to be working
this new file is not being added so never committed

2021-03-14

- ran the build in an outside directory
   installed simple-git before build and got a smaller set of dependency warnings
   but reading documentation leads me to think these are not relevant to running the code in the Obsidian client (I may be wrong)
   
 - so now we wait to see what happens when the git push command is triggered ....

2021-03-14  11:19
- noticed that "disable push" was set "On"; must have missed that earlier (double-negatives - Bah!)
- so let's see what happens in the next 5 - 8 minutes re `push`

