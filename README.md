How to write "Hello/Howdy/Hiya, world!" and deploy to
[Heroku](http://www.heroku.com/) in about 60 seconds:

    $ pip install Keystone
    $ cat << EOF > index.ks
    import random
    greeting = random.choice(['Hello', 'Howdy', 'Hiya'])
    ----
    <!doctype html>
    <html
      <head>
        <title>{{greeting}}, world!</title>
      </head>
      <body>
        <h1>{{greeting}}, world!</h1>
        <p>How's it going?</p>
      </body>
    </html>
    EOF
    $ keystone --configure heroku
    $ git init
    $ git add index.ks Procfile requirements.txt wsgi.py
    $ git commit -m "demo app for python.herokuapp.com"
    $ heroku apps:create --stack cedar keystone-heroku-demo
    $ git push heroku master

That's it!

----

Want to learn more about Keystone? Check out the
[documentation](http://keystone.readthedocs.org) hosted by [Read the
Docs](http://readthedocs.org/), or [fork
Keystone](https://github.com/dcrosta/keystone) just over there on
[GitHub](https://github.com/).

