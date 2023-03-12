# Terminal Commands
These are a few helpful commands you'll likely use during this cohort (once we start in machine setup, Node and the backend)

## Basic Terminal Commands
- Command line
  - See where I am `pwd`
  - list files `ls`
  - list hidden files `ls -a`
  - change directory `cd <directory-name>`
  - Open whole directory in VS Code `code .`
  - shorthand for current and previous directory
    - `ls .` lists current directory
    - `ls ..` lists previous directory
    - `cd ..` moves up a directory
  - home vs root
    - `~` is short for home
    - `cd ~` brings you home
    - `/` is short for root
    - `cd /` brings to you root
  - absolute vs relative paths
    - **Absolute**: `touch /directory-name/file-name.txt` goes to the root directory, into `directory-name`, makes a file inside of that directory
    - **Relative**: `touch ./directory-name/file-name.txt` goes into `directory-name` from current level, makes a file inside of that directory
    - `touch ~/directory-name/file-name.txt` goes into your home directory (usually looks like `/home/username`)
  - Files
    - create files `touch file-name.txt`
    - remove a file `rm file-name.txt`
    - rename a file `mv file-name.txt new-file-name.txt`
    - move a file `mv this.txt target-directory/`
  - Directorys
    - create directorys `mkdir directory-name`
    - remove a directory `rm directory-name -R`
    - rename a directory `mv directory-name new-directory-name`
    - move a directory `mv directory-name ../../target-directory`

## Git
- Cloning and remotes
  - Clone `git clone <url>`
  - Check where cloning from and committing to `git remote -v`
  - Add a remote repository  `git remote add <remote-name> https://remote-url/repo-name.git`
  - Change the origin `git remote set-url origin <new-git-repo-url>`
- Committing
  - See status of staging area etc `git status`
  - Add all files in the repo to staging area `git add -A` or `add .`
    - Alternatively: Add just one file to the staging area `git add <filename>`
  - Commit `git commit -m "my-message"`
  - Push `git push` or `git push origin master`
- Branching
  - Check out to a new branch `git checkout -b <branchname>`
  - Check out to an existing branch `git checkout <branchname>`
  - Delete a branch (cannot be the branch you're on!) `git branch -D <branchname>`
  - Merge another branch into current branch
    1. Move to the branch you want to merge FROM `git checkout dev`
    2. Pull down most recent remote version `git pull`
    3. Move to the branch you want to merge TO `git checkout feature-branch-#25`
    4. Merge the FROM branch (`dev` in this case) into the current branch `git merge dev`
- Logs
  - See log of activity (commits) `git log`
  - See log with limited info (easier to read) `git log --oneline`
- Configs
  - See git repo config settings (i.e. email username etc): `git config --list`
  - Change git email locally: `git config user.name "Marley McTesterson"`
  - Change git email locally: `git config user.email example@email.com`
  - Change git core editor: `git config --global core.editor "code --wait"`
- Diffs
  - See what is changed currently compared to the most recent commit `git diff`
  - See what has changed in the current working tree vs a specific branch `git diff <branch-name> --`
- Removing/rebasing changes - Intermediate to Advanced
  - Remove uncommitted changes (but save them for later, just in case) `git stash`
  - Remove last commit `git reset --hard HEAD^`
  - Squash the last 3 commits into one single commit `git rebase -i HEAD~3`
    - Then in the editor, for any commits you want to keep leave `pick`. For anything you want to "squash" and not include that as a commit, change `pick` to `squash`.
  - Squash everything after <SHA1> `git rebase -i e25340b` where e25340b is the SHA1
    - Repeat next step from above to pick/squash specific  commits.

## ports/processes
- Show what is running on a port `lsof -i:<port-number>`
- Kill a process `kill <process-id>`
- Example of above two steps
```sh
$ lsof -i:3000
COMMAND   PID    USER   FD   TYPE            DEVICE SIZE/OFF NODE NAME
node     78070 myuser   24u  IPv6 0xdc9d8g07c355e5f      0t0  TCP *:hbci (LISTEN)

$ kill 78070
```
- Show list of all node processes `ps -ef | grep node`
- Kill all node processes `pkill -f node`

## heroku
- Create a new app `heroku create`
- Create a named app `heroku apps:create <app-name>`
- Rename your app (changes the domain too) `heroku apps:rename <new-app-name>`
- Push code to heroku `git push heroku master`
- Set an environment variable `heroku config:set VAR_NAME="variable-value"`
- Open the heroku app from the current project `heroku open`
- Run a script on your app's terminal. `heroku run <command>` (example: `heroku run npm run seed`)
- Try destroying the old app: `heroku apps:destroy <app-name>` Note that this will *__PERMANENTLY__* and irrevocably destroy the app.  If an app name is not provided, the current heroku app will be assumed, and user will be prompted for confirmation.
- Edit the heroku git remote: ` heroku git:remote -a <app-name>`
- Add a pre-existing heroku app to my current local repo: `heroku git:remote -a <app-name>`
  - This gives access to the `heroku run` and `heroku logs --tail` etc commands above.

## PostgreSQL
- Start PostgreSQL `sudo service postgresql start`
- Restart PostgreSQL `sudo service postgresql restart`
- Create a database `createdb my-database-name`
- Enter PSQL command line `psql`, and then these are a few of the commands that are available:
  - Connect to a previously-created database `\c my-database-name`
  - Create a table
  ```sql
  CREATE TABLE users (
    id SERIAL PRIMARY KEY
  );
  ```
  - Describe table `\d`
  - Drop table `DROP TABLE users;`
### PostgreSQL on MacOS:
- If, when trying to run `psql` from command line, you get an error similar to ...
```sh
psql: could not connect to server: No such file or directory
	Is the server running locally and accepting
	connections on Unix domain socket "/tmp/.s.PGSQL.5432"?
```
- ...then PostgreSQL is not running. To start it, open PostgreSQL and click Start.  If you get an error `stale postmaster.pid file`, the solution should be as follows:
  - for most cases this can be resolved by running `rm ~/Library/Application Support/Postgres/var-11/postmaster.pid`
  - If not, follow [these instructions](https://medium.com/@mccarthyd/postgres-postmaster-pid-errors-5bdf3c2522fd)
  - Finally, click Start in Postgres, and it should work this time without an error.

## cURL
- Methods
  - `GET` request: `curl https://www.google.com/`
  - `PATCH` request: `curl http://localhost:3000/myroute -X PATCH -H 'Content-Type: application/json' -d '{"key1": "val1", "key2": "val2"}'` (`-H` is a header, in this case setting our content type as json.)
  - `POST` request: `curl http://localhost:3000/myroute -H "Content-Type: application/json" -H "Authorization: Bearer <myreallylongtoken>" -X POST -d '{"key1": "val1", "key2": "val2"}'` (the two `-H`s are our headers, in this case (1) setting our content type as json and (2) sending our token via the Authorization header. `-X` is setting the method, post in this case. `-d` is the request body in JSON format.)
  - `DELETE` request: `curl http://localhost:3000/myrouote -X DELETE`
- Setting Authorization header: `curl http://localhost:3000/myroute -H 'Authorization: Bearer <myreallylongtoken>'`

## WSL / Ubuntu
- Equivalent Commands
|Operation                                  |WSL Ubuntu       |MacOS      |
|---                                        |---              |---        |
|Open current directory/folder in Explorer  |`explorer.exe .` |`code .`   |
- Drive/Directory Mapping (where all your files are)
  - C drive directory in Windows Explorer is `/mnt/c` in ubuntu terminal
  - `\\wsl$\Ubuntu\home\preston` is the windows path for the ubuntu "home" dir (where `cd ~` takes you).  This is a network drive.
