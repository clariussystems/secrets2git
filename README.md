Managing secrets correctly is a giant pain that nobody does right.
secrets2git attempts to fix that by making secure management of secrets easy
and straightforward.

How?
secrets2git simply encrypts secrets into source where they can be encrypted
and decrypted with git hooks.

KMS for encryption
secrets2git uses KMS to meet the most stringent compliance requirements and
ensure the master key is never stored or seen by anyone.

Setup
-----
1. Copy this file into your repo's root directory.
2. Install requirements:
   [optionally use a virtualenv or anaconda environment]
   pip install -r secrets2git_requirements.txt
3. Create a git push and pull hook that run the file you copied, i.e.:
   echo python secrets2git.py pull >> .git/hooks/pre-pull
   echo python secrets2git.py push >> .git/hooks/pre-push
4. Set the config below

Notes:
-
- Okay to require internet connection on git pull/push since git usually
  needs it anyway.
-
- Git submodule as a distribution mechanism, cuz it's Git!
