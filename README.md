# snippet-error-poc

```
npx testdriverai@latest run testdriver/test.yaml 
Need to install the following packages:
testdriverai@6.0.29
Ok to proceed? (y) y

Log file created at: /var/folders/7s/2nhyb0rj2bs_rkswlgqnnhdm0000gn/T/testdriverai-cli-17920.log
Howdy! I'm TestDriver v6.0.29
Starting debugger server...
This is beta software!
Join our Discord for help
https://discord.com/invite/cWDFW8DzPm
Working on /Users/ianjennings/Development/snippet-error-poc/testdriver/test.yaml
establishing connection...
error:fatal : Validation Failure
Path:      
Schema:    #/required
Keyword:   required
Missing:   version
Message:   must have required property 'version'


authenticating...
no recent sandbox found, creating a new one.
creating new sandbox (can take up to 2 minutes)...
connecting...
Live test execution: 
http://localhost:55140?data=%7B%22resolution%22%3A%5B1366%2C768%5D%2C%22url%22%3A%22http%3A%2F%2F3.144.171.24%3A8080%2Fvnc_lite.html%3Ftoken%3DV3b8wG9%22%2C%22token%22%3A%22V3b8wG9%22%7D
running /Users/ianjennings/Development/snippet-error-poc/testdriver/test.yaml...
error:fatal : Validation Failure
Path:      
Schema:    #/required
Keyword:   required
Missing:   version
Message:   must have required property 'version'



> snippet run
test.yaml:2:4 (run)
command='run' file='snippet.yaml'
snippet.yaml (start)
error:fatal : Validation Failure
Path:      
Schema:    #/required
Keyword:   required
Missing:   version
Message:   must have required property 'version'


snippet.yaml:2:4 (exec)
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

   1     steps:
   2       - prompt: snippet postrun
   3         commands:
   4 >>>     - command: exec
   5           lang: js
   6           output: validation_result
   7           code: throw new Error('Validation failed')

Error: Error running script: Validation failed
reviewing test...
summarizing...
    The test was intended to automate a simple desktop
    flow—most likely focusing Google Chrome (or another
    browser), clicking into its address bar, and typing a URL
    or search term—but it never actually succeeded. When the
    runner tried to parse and execute the generated YAML, it
    hit a “Validation failed” error because the script didn’t
    conform to the strict schema (it included blank lines and
    comments, omitted required fields like unique description
    attributes, and didn’t properly focus or verify the
    correct application window before issuing input commands).
    As a result, the test engine couldn’t validate the steps
    and aborted before performing any real UI actions.

Summary written to: /var/folders/7s/2nhyb0rj2bs_rkswlgqnnhdm0000gn/T/testdriver-summary.md
exiting...
running /Users/ianjennings/Development/snippet-error-poc/testdriver/lifecycle/postrun.yaml...
error:fatal : Validation Failure
Path:      
Schema:    #/required
Keyword:   required
Missing:   version
Message:   must have required property 'version'



> POSTRUN RUNNING
postrun.yaml:2:4 (exec)
exec
command='exec' code='echo "POSTRUN"' lang='pwsh'
calling exec...
echo "POSTRUN"
Command stdout:

```
