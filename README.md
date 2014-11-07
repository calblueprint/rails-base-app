Rails Base App
====

A starter app for development using Ruby on Rails. It comes with gems that are
widely used across most apps and many handy development and test gems.

Ruby version: ```2.1.4``` <br>
Rails version: ```4.1.7```

Core gems:

- ```thin``` for server
- ```pg``` for database
- ```figaro``` for env config on development/Heroku
- ```devise``` for authentication
- ```simple_form``` for forms
- ```gon``` for javascript variables
- ```kaminari``` for pagination
- SASS, Coffeescript, Slim, and autoprefixer for frontend


## Requirements

- git
- Ruby version 2.1.4 (best installed with [RVM](https://rvm.io/))
- [direnv](https://github.com/zimbatm/direnv) if you want to avoid typing
```bin``` all the time for [spring](https://github.com/rails/spring/blob/master/README.md)

## Getting Started
1. Clone the repo:

        git clone https://github.com/calblueprint/rails-base-app/ <your project name>

2. Change the .ruby-gemset file if needed so that RVM selects the right gemset
for your project. The default gemset is called ```base-app```

3. ```cd``` into your project directory and run ```bundle install```.

4. Copy over ```config/database.yml.sample``` into ```config/database.yml``` and
change the settings for the database names and your postgres credentials.

5. Copy over ```config/application.yml.sample``` into ```config/application.yml```
and add any environment variables as necessary (figaro loads them for you).

6. In ```config/application.rb```, change the line

        module RailsBaseApp

    to

        module <your app name>

    In ```/config/initializers/session_store.rb```, change the key name to your
    app name.

7. Run ```rake db:create``` and ```rake db:migrate```.
8. Run ```rspec``` to make sure that rspec works.

### Optional but nice
1. Install the [LiveReload Chrome extension](https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei?hl=en) - when you start guard, it'll reload
your browser when a matching file is changed!
2. Set up [Code Climate](https://codeclimate.com/) for your project.
3. Set up [Travis](https://travis-ci.org/) for your project - integrate test
coverage with Code Climate for a double win! You'll have to enter in your Code
Climate token in ```.travis.yml```

## Developing
Have one terminal tab open for each of:

- ```rails s```
- ```guard```
- ```bash```

Happy developing!

## Deploying
Deploying to Heroku is the same as any other application. However, since we have
figaro, to set your environment variables on Heroku you can just run

    figaro heroku:set -e production

The base app also comes with ```rollbar```, which is an error logging service
for Rails. [After setting it up](https://rollbar.com/), you can fill in the
tokens in your ```config/application.yml``` file.

The New Relic gem is also installed, and you can follow the instructions after
starting the service on Heroku.

To use Google Analytics, edit the keys in ```config/application.yml```
once it's set up.

## Contributing

Feel free to open issues or send pull requests with improvements. Thanks in
advance for your help!

## Cal Blueprint
![bp](http://bptech.berkeley.edu/assets/logo-full-large-d6419503b443e360bc6c404a16417583.png "BP Banner")
**[Cal Blueprint](http://www.calblueprint.org/)** is a student-run UC Berkeley organization devoted to matching the skills of its members to our desire to see social good enacted in our community. Each semester, teams of 4-5 students work closely with a non-profit to bring technological solutions to the problems they face every day.

## License

![Creative Commons License](http://i.creativecommons.org/l/by/3.0/88x31.png)
This work is licensed under a [Creative Commons Attribution 3.0 Unported
License](http://creativecommons.org/licenses/by/3.0/deed.en_US)
