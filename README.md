Sample Crystal application
======================================

Running Locally
---------------

First, you need to have a working crystal environment:

http://crystal-lang.org/docs/installation/

You can specify the listening port using the --port flag

### Test
```sh
crystal src/scalingo01.cr -- --port 9090
```

### Build
```sh
crystal build src/scalingo01.cr --release
```

### Execute
```sh
./scalingo01 --port 9090
```

Deploying on Scalingo
---------------------

Create an application on https://scalingo.com, then:

```
git remote add scalingo git@scalingo.com:<name_of_your_app>.git
```
Set the `BUILDPACK_URL` environement variable to `https://github.com/crystal-lang/heroku-buildpack-crystal.git`.

You can do it using the web dashboard, select your application, go to the `Environment` tab and add :
```
BUILDPACK_URL=https://github.com/crystal-lang/heroku-buildpack-crystal.git
```

If you want to do it using the scalingo cli interface juste type :
```sh
scalingo -a <name_of_your_app> env-set BUILDPACK_URL=https://github.com/crystal-lang/heroku-buildpack-crystal.git
```

Next you'll need to push it to scalingo :
```sh
git push scalingo master
```

And that's it!

The application is running at this url: https://sample-crystal.scalingo.io

Deploy in one click
-------------------

[![Deploy to Scalingo](https://cdn.scalingo.com/deploy/button.svg)](https://my.scalingo.com/deploy)

Links
-----
http://crystal-lang.org/
