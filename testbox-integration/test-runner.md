# Run unit test suite from the command line

There is a `testbox run` command available that will run your unit or integration tests from the command line.  All you need is to have your server running (it doesn't have to be a CommandBox server).

Run your test suite like so (modify the runner URL to match your site).
```
testbox run "http://localhost:8080/tests/runner.cfm"
```

This will hit your runner URL and output a CLI-formatted report of your test results.  If your test suite failed, the command will also return a failing status code when being run from your native shell.  This makes integrations with CI tools like Jenkins or Travis-CI very easy since a failing test will fail your build automatically.

## Default runner URL

You can also set up the default runner URL in your box.json and it will be used for you.  Setting the URL is a one-time operation.

```
package set testbox.runner="http://localhost:8080/tests/runner.cfm"
testbox run
```
