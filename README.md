


![](https://github.com/rgpravin/spanimages/blob/main/git.png)


# DevSecOps 

***Pre-Commit Hook Tool***

Description

* A pre-commit hook is a client-side git hook that runs right before the commit is created. 
* Pre-commit hook is run first when committing, before you even type in a commit message. 
* It’s used to inspect the snapshot that’s about to be committed, to see if you’ve forgotten something, to make sure tests run, or to examine whatever you need to inspect in the code.
* Pre-commit hooks can be a useful way to enforce certain policies or standards within a team, or to ensure that the codebase is always in a good state before changes are made
## Usage/Examples
1. Go to the desired folder(source-code) and install the pre commit 
```bash
pip3 install pre-commit
```
**Note:** Please upgrade your python by typing the following command 
  ```bash
 python.exe -m pip install --upgrade pip
  ```
2. Create an .pre-commit-config.yaml file
```bash
touch .pre-commit-config.yaml
```
3. Open the created .yaml file and paste the following command and save the file
```bash
repos:
  - repo: https://github.com/gitguardian/ggshield
    rev: v1.14.2
    hooks:
      - id: ggshield
        language_version: python3
        stages: [commit]
```
**Note**: To scan all the sub folder please replace the code with the directory that you want to scan. my_dir represents the sub-folder
  ```bash
 exclude: ^my_dir/ 
repos:
  - repo: https://github.com/gitguardian/ggshield
    rev: v1.14.2
    hooks:
      - id: ggshield
        language_version: python3
        stages: [commit]
  ```
4. Create a hook type (pre-push using pre-commit) command 
```bash
$ pre-commit install
pre-commit installed at .git/hooks/pre-commit
```
5. Create an .env file and go to git guardian site (https://www.gitguardian.com/) and Create an Account

![App Screenshot](https://github.com/rgpravin/spanimages/blob/main/gitguardian.png)

6. Create a new token in gitguardian 

![App Screenshot](https://github.com/rgpravin/spanimages/blob/main/token.png)

7. Once the token is created, copy and paste in the .env file 

![App Screenshot](https://github.com/rgpravin/spanimages/blob/main/git%20token.png)


![App Screenshot](https://github.com/rgpravin/spanimages/blob/main/env%20file.png)

8. We should specify the .env file in the gitignore folder as you dont want to leak the credentials

9. Now run  the command to commit, GGshield will be up and will scan for harcoded secrets in the code
## Feedback

If you have any feedback, please reach out to us at appsec@spantechnologyservices.com


## Reference

https://docs.gitguardian.com/ggshield-docs/integrations/git-hooks/pre-commit

https://blog.gitguardian.com/setting-up-a-pre-commit-git-hook-with-gitguardian-shield-to-scan-for-secrets/

https://www.youtube.com/watch?v=ySTG2NODQCg