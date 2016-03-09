# go-kext-monitor
Watch your kernel modules that Apple might be touching in secret.

Frustrated with the lack of an **inotify** for OSX and the recent discovery that Apple was breaking macs in Feb 2016 by giving us an ethernet "fix" we didn't want or probably need, AFAIK. I hope itr wasn't in response to a request outside the company!

Regardless of the motivations, Apple made changes in secret to our machines.

I looked for an inotify option to track changes to kext directories in the future. Specifically the /Volumes/Macintosh\ HD/System/Library/Extensions/AppleKextExcludeList.kext/ folder which gave away at least one of the *two* changes they made. I didn't find one so I wrote one using go-fsevents.

**Prerequisites**

You will need to install fsevents.

`go get github.com/go-fsnotify/fsevents`

**Running**

`go run go-kext-monitor`

You will get a running log of changes in the directory.

More changes are planned but I wanted to share it in case it helps anyone.

**Stopping**

`ctrl+c` to halt the app at any time.
