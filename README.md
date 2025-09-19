# snippet-error-poc

```
npx testdriverai@latest run testdriver/test.yaml
Need to install the following packages:
testdriverai@6.0.30
Ok to proceed? (y) y

Log file created at: /var/folders/7s/2nhyb0rj2bs_rkswlgqnnhdm0000gn/T/testdriverai-cli-22865.log
Howdy! I'm TestDriver v6.0.30
Starting debugger server...
This is beta software!
Join our Discord for help
https://discord.com/invite/cWDFW8DzPm
Working on /Users/ianjennings/Development/snippet-error-poc/testdriver/test.yaml
establishing connection...
authenticating...
no recent sandbox found, creating a new one.
creating new sandbox (can take up to 2 minutes)...
connecting...
Live test execution: 
http://localhost:60088?data=%7B%22resolution%22%3A%5B1366%2C768%5D%2C%22url%22%3A%22http%3A%2F%2F18.191.211.115%3A8080%2Fvnc_lite.html%3Ftoken%3DV3b8wG9%22%2C%22token%22%3A%22V3b8wG9%22%7D
running /Users/ianjennings/Development/snippet-error-poc/testdriver/test.yaml...

> snippet run
test.yaml:3:5 (run)
command='run' file='snippet.yaml'
snippet.yaml (start)
snippet.yaml:3:5 (exec)
exec
command='exec' code='throw new Error('Validation failed')' lang='js'
calling exec...
throw new Error('Validation failed')
running js...
running value of `windows` in local JS vm...

------
error:general : Error detected, but recovery mode is not enabled.
To attempt automatic recovery, re-run with the --heal flag.
error:fatal : Error in snippet.yaml:

   2     steps:
   3       - prompt: snippet postrun
   4         commands:
   5 >>>     - command: exec
   6           lang: js
   7           output: validation_result
   8           code: throw new Error('Validation failed')

Error: Error running script: Validation failed
reviewing test...
summarizing...
    It looks like the test never actually executed any UI
    steps because its mission statement was left blank and no
    commands were defined to drive the application, so when
    the runner tried to validate the YAML it found required
    fields (like a non-empty goal and at least one action)
    missing or malformed. In other words, the script was
    syntactically valid YAML but semantically failed the test
    harness’s schema checks—there was nothing to focus, click,
    or assert—so the validator refused to run it and reported
    “Validation failed.”

Summary written to: /var/folders/7s/2nhyb0rj2bs_rkswlgqnnhdm0000gn/T/testdriver-summary.md
exiting...
running /Users/ianjennings/Development/snippet-error-poc/testdriver/lifecycle/postrun.yaml...

> POSTRUN RUNNING
postrun.yaml:3:5 (exec)
exec
command='exec' code='echo "POSTRUN"' lang='pwsh'
calling exec...
echo "POSTRUN"
Command stdout:
POSTRUN
```
