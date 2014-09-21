cmdcache
========

```
Usage: cmdcache [options]

Options:
  -h, --help            show this help message and exit
  -e ENVIRONMENT, --environment=ENVIRONMENT
                        indicate that output depends on the environment
                        variable value (and presence)
  -f FILE_CONTENTS, --file-contents=FILE_CONTENTS
                        indicate that output depends on the file contents
  --cache-dir=CACHE_DIR
                        specify cache directory (~/.cmdcache/ by default)
  -v, --verbose         Be verbose and print debug messages
  -r, --check-relative-path
                        Make additional check on the executable path if
                        it is not absolute.                 If the path is
                        relative to current directory                 (i.e.
                        begins with './') additionally hash $PWD.
                        Otherwise additionally hash output of 'which CMD'.
  --no-stdin            Completely ignore stdin and don't hash its contents.
                        Can be usefull in case the executable doesn't read
                        anything from stdin.

cmdcache executes a program and caches its output.
It is assumed that there are no side effects of the program execution
and the data written to stdout depends strictly on the known data.
This data includes: stdin contents, program name, program arguments,
environment variables (only if -e option is given), files contents
(only if -f option is given).

Examples:

    cmdcache -f file -- egrep REGEXP file
    cmdcache -e PATH -- which id
```
