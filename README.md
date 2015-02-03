Flask App
============

What is this?
-------------

This is a template to help you get a 
[Flask](http://flask.pocoo.org/) app running on
[Heroku](https://www.heroku.com/).

It is based on [flask_heroku](github.com/zachwill/flask_heroku)

But follows the structure from the [Flask megatutorial](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world)

We also removed the dependency on gevent


Prerequisites
-------------

It is assumed that you've installed the heroku toolbelet](http://toolbelt.heroku.com)

Instructions
------------

Clone the repo.

    git clone git@github.com:info3180/flask_app.git
    cd flask_app
    
To clear the git history, remove the .git/ folder
 
    rm -rf .git/


For your convenience, the project ships with a virtualenv script which means you
can quickly create a virtual environment using the following commands

    python virtualenv.py --no-site-packages venv
    source venv/bin/activate


Installing Packages
--------------------

### pip

Then, let's get the requirements installed in your isolated test
environment.

    $ pip install -r requirements.txt


Running Your Application
------------------------

Activate your virtualenv

    source venv/bin/activate

Now, you can run the application locally.

    python run.py


Deploying
---------

If you haven't [signed up for Heroku](https://api.heroku.com/signup), go
ahead and do that. You should then be able to [add your SSH key to
Heroku](http://devcenter.heroku.com/articles/quickstart), and also
`heroku login` from the commandline.

Now, to upload your application, you'll first need to do the
following -- and obviously change `app_name` to the name of your
application:

    heroku create app_name -s cedar

And, then you can push your application up to Heroku.

    git push heroku master
    heroku scale web=1

Finally, we can make sure the application is up and running.

    heroku ps

Now, we can view the application in our web browser.

    heroku open

And, to deactivate `virtualenv` (once you've finished coding), you
simply run the following command:

    deactivate


Next Steps
----------

After you've got your application up and running, there a couple next
steps you should consider following.

1. Create a new `README.md` file.
2. Add your Google Analytics ID to the `base.html` template.
3. Adjust the `author` and `description` `<meta>` tags in the
   `base.html` template.
4. Change the `humans.txt` and `favicon.ico` files in the `static`
   directory.
5. Change the `apple-touch` icons in the `static` directory.


Reactivating the Virtual Environment
------------------------------------

If you haven't worked with `virtualenv` before, you'll need to
reactivate the environment everytime you close or reload your terminal.

    $ source venv/bin/activate

If you don't reactivate the environment, then you'll probably receive a
screen full of errors when trying to run the application locally.


Adding Requirements
-------------------

In the course of creating your application, you may find yourself
installing various Python modules with `pip` -- in which case you'll
need to update the `requirements.txt` file. One way that this can be
done is with `pip freeze`.

    $ pip freeze > requirements.txt


Custom Domains
--------------

If your account is verified -- and your credit card is on file -- you
can also easily add a custom domain to your application.

    $ heroku addons:add custom_domains
    $ heroku domains:add www.mydomainname.com

You can add a [naked domain
name](http://devcenter.heroku.com/articles/custom-domains), too.

    $ heroku domains:add mydomainname.com

Lastly, add the following A records to your DNS management tool.

    75.101.163.44
    75.101.145.87
    174.129.212.2
