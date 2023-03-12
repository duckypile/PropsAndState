# Deploy Node / PG App w fly.io

### First do these things:

- [Install Fly.io](https://fly.io/docs/hands-on/install-flyctl/)

- [Sign up](https://fly.io/docs/hands-on/sign-up/)

- [Sign in](https://fly.io/docs/hands-on/sign-in/)

### Then...

#### Create and Deploy from a Project Folder

- To create the app run:
  `flyctl launch`

- You will be prompted to setup a postgresql db, select yes
  `? Would you like to set up a Postgresql database now? Yes`

- PICK A REGION CLOSEST TO YOU!!

- Sometimes this command does fail, and you will get an error:
  `Error Failed attaching bitter-darkness-1528-db to the Postgres cluster bitter-darkness-1528: Get "http://bitter-darkness-1528-db.internal:5500/commands/databases/bitter_darkness_1528": dial: lookup bitter-darkness-1528-db.internal. on fdaa:0:bfc7::3: no such host.\nTry attaching manually with 'fly postgres attach --app bitter-darkness-1528 bitter-darkness-1528-db'`

#### Errors are our friends, it even tells us to try attaching manually!

- last part of the error is what we need!

- WARNING: I have found that it's best to wait a few minitues, then try attaching the db manually with:
  `fly postgres attach --app bitter-darkness-1528 bitter-darkness-1528-db` <- Replace w ur app names

- Next, if you have any seed scripts to run, you can add them to the `fly.toml` file

```
[deploy]
  release_command = "npm run seed"
```

#### To set secrets: [HERE](https://fly.io/docs/reference/secrets/#setting-secrets)

- finally, after you have set any secrets in your application, you can run:
  `fly deploy`

### Wish you the best, much success!
