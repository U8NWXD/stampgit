# `stampgit`: Trusted Timestamping for Git Commits

Git does a great job of tracking revisions to a repository, but having
a revision history doesn't *prove* that the history is accurate. After
all, we can rewrite git history using `git reset`. Even with remote
repositories, force-pushing is often available.

In some situations, we want this kind of proof. For example, you might
want to prove that you had developed a piece of software first, or you
might want to be able to prove that your digital notebook was written
contemporaneously and hasn't been modified. [Trusted
timestamping](https://en.wikipedia.org/wiki/Trusted_timestamping) gives
us a way to prove that an arbitrary piece of data existed at a
particular time. In this case, we want to prove that a git commit
existed, so we timestamp the commit hash. Since this hash depends on the
entire git history, it being timestamped proves that the history prior
to that commit hasn't been changed since that date.

## Usage

For documentation, see `./stampgit.sh -h`. Here's a quick overview:

* To create a timestamp: `./stampgit.sh create [commit hash]`
* To verify a timestamp: `./stampgit.sh verify [commit hash]`
* To see the details of a timestamp: `./stampgit.sh examine [commit hash]`
* To remove a timestamp: `./stampgit.sh remove [commit hash]`

If you leave off `[commit hash]`, `HEAD` is assumed.

## Acknowledgements

This script is adapted from Ryan J's question on Code Review
Stackexchange at
[https://codereview.stackexchange.com/q/15380](https://codereview.stackexchange.com/q/15380)
. The original script is licensed under CC-BY-SA.

## Legal

### Disclaimer

When I discuss proving something, I do not mean to suggest that
timestamping meets any kind of legal or evidentiary standard. Timestamps
from this tool may not be acceptable for your particular situation.
Nothing here is legal advice, and you should consult a lawyer if you
have legal questions.

### Copyright

Copyright (c) 2020 U8N WXD

### License

This work is licensed under a [Creative Commons Attribution Share-Alike
4.0 International
License](https://creativecommons.org/licenses/by-sa/4.0/)

![Creative Commons License](https://licensebuttons.net/l/by-sa/4.0/88x31.png)

See [`LICENSE.txt`](LICENSE.txt) for the full license.
