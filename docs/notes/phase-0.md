1. Why do we use a branch and a pull request, even working alone?
Ans:- A branch allows isolated development without affecting the main code. A pull request helps review and verify changes before merging, even when working alone.
2. What do .gitignore and detect-private-key each protect against?
Ans:- .gitignore prevents sensitive or unnecessary files from being tracked by Git. detect-private-key scans commits for accidentally exposed private keys.
3. What happened when you tried to commit the fake key, and why isn’t a local hook enough on its own?
Ans:- The commit was blocked because the local security hook detected the fake private key. A local hook alone isn't enough because it can be bypassed or disabled, so server-side checks are also necessary.
