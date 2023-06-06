Note that this package is not intended to have active maintenance, so reviews may be slow.

Expected behaviors:

- if someone has `postinstall` available to them on their system, they should see a message about being encouraged to use `ember-cli` instead of `ember`.
    - Docs on `install`: https://docs.npmjs.com/cli/v9/using-npm/scripts#npm-install
    - Docs on `ignore-scripts`: https://docs.npmjs.com/cli/v9/using-npm/config#ignore-scripts
        - Default is false, but _should_ be true for security reasons (until Node 20's fine grained fs permissions, anyway)
- after having accidentally installed `ember` instead of `ember-cli`, we want to forward commands to `ember-cli`, so that folks can remain productive. However, messaging also prints encouraging users to install the correct tool (`ember-cli`).
- the exit code from the underlying `ember-cli` process, if invoked, should be forwarded to the invoking shell

To test that all of this works:

## Local Testing

You need to install the local copy of the package globally.
If you already have `ember-cli` installed, you'll need to uninstall that as it provides the `ember` bin.

you can install the local copy of this tool via `npm install -g .`
However, this does not trigger `postinstall`, regardless of your `ignore-scripts` setting.



