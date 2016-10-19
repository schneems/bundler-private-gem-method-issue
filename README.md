Install gems

```
bundle install
```

Load Rakefile

```
$ bundle _1.13.5_ exec rake -T
rake aborted!
private method `gem' called for #<Rails::Application::Configuration:0x007fa7ff8698a0>
Did you mean?  gets
/Users/richardschneeman/.gem/ruby/2.3.1/gems/railties-3.2.22.2/lib/rails/railtie/configuration.rb:85:in `method_missing'
/Users/richardschneeman/Documents/projects/tmp/bundler_issue/config/application.rb:10:in `<class:Application>'
/Users/richardschneeman/Documents/projects/tmp/bundler_issue/config/application.rb:9:in `<module:Foo>'
/Users/richardschneeman/Documents/projects/tmp/bundler_issue/config/application.rb:8:in `<top (required)>'
/Users/richardschneeman/Documents/projects/tmp/bundler_issue/Rakefile:4:in `require'
/Users/richardschneeman/Documents/projects/tmp/bundler_issue/Rakefile:4:in `<top (required)>'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/lib/bundler/cli/exec.rb:74:in `load'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/lib/bundler/cli/exec.rb:74:in `kernel_load'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/lib/bundler/cli/exec.rb:27:in `run'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/lib/bundler/cli.rb:332:in `exec'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/lib/bundler/vendor/thor/lib/thor/command.rb:27:in `run'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/lib/bundler/vendor/thor/lib/thor/invocation.rb:126:in `invoke_command'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/lib/bundler/vendor/thor/lib/thor.rb:359:in `dispatch'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/lib/bundler/cli.rb:20:in `dispatch'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/lib/bundler/vendor/thor/lib/thor/base.rb:440:in `start'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/lib/bundler/cli.rb:11:in `start'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/exe/bundle:34:in `block in <top (required)>'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/lib/bundler/friendly_errors.rb:100:in `with_friendly_errors'
/Users/richardschneeman/.gem/ruby/2.3.1/gems/bundler-1.13.5/exe/bundle:26:in `<top (required)>'
/Users/richardschneeman/.gem/ruby/2.3.1/bin/bundle:23:in `load'
/Users/richardschneeman/.gem/ruby/2.3.1/bin/bundle:23:in `<main>'
(See full trace by running task with --trace)
```

Fails for Newer versions of bundler, works in older versions such as 1.11.2.

```
$ bundle _1.11.2_ exec rake -T
rake about              # List versions of all Rails frameworks and the environment
rake assets:clean       # Remove compiled assets
rake assets:precompile  # Compile all the assets named in config.assets.precompile
rake db:create          # Create the database from DATABASE_URL or config/database.yml for the current Rails.env (use db:create:all to create all dbs in the config)
rake db:drop            # Drops the database using DATABASE_URL or the current Rails.env (use db:drop:all to drop all databases)
rake db:fixtures:load   # Load fixtures into the current environment's database.
rake db:migrate         # Migrate the database (options: VERSION=x, VERBOSE=false).
rake db:migrate:status  # Display status of migrations
rake db:rollback        # Rolls the schema back to the previous version (specify steps w/ STEP=n).
rake db:schema:dump     # Create a db/schema.rb file that can be portably used against any DB supported by AR
rake db:schema:load     # Load a schema.rb file into the database
rake db:seed            # Load the seed data from db/seeds.rb
rake db:setup           # Create the database, load the schema, and initialize with the seed data (use db:reset to also drop the db first)
rake db:structure:dump  # Dump the database structure to db/structure.sql. Specify another file with DB_STRUCTURE=db/my_structure.sql
rake db:version         # Retrieves the current schema version number
rake doc:app            # Generate docs for the app -- also available doc:rails, doc:guides, doc:plugins (options: TEMPLATE=/rdoc-template.rb, TITLE="Custom Title")
rake log:clear          # Truncates all *.log files in log/ to zero bytes
rake middleware         # Prints out your Rack middleware stack
rake notes              # Enumerate all annotations (use notes:optimize, :fixme, :todo for focus)
rake notes:custom       # Enumerate a custom annotation, specify with ANNOTATION=CUSTOM
rake rails:template     # Applies the template supplied by LOCATION=(/path/to/template) or URL
rake rails:update       # Update configs and some other initially generated files (or use just update:configs, update:scripts, or update:application_controller)
rake routes             # Print out all defined routes in match order, with names.
rake secret             # Generate a cryptographically secure secret key (this is typically used to generate a secret for cookie sessions).
rake stats              # Report code statistics (KLOCs, etc) from the application
rake test               # Runs test:units, test:functionals, test:integration together (also available: test:benchmark, test:profile, test:plugins)
rake test:recent        # Run tests for {:recent=>"test:prepare"} / Test recent changes
rake test:single        # Run tests for {:single=>"test:prepare"}
rake test:uncommitted   # Run tests for {:uncommitted=>"test:prepare"} / Test changes since last checkin (only Subversion and Git)
rake time:zones:all     # Displays all time zones, also available: time:zones:us, time:zones:local -- filter with OFFSET parameter, e.g., OFFSET=-6
rake tmp:clear          # Clear session, cache, and socket files from tmp/ (narrow w/ tmp:sessions:clear, tmp:cache:clear, tmp:sockets:clear)
rake tmp:create         # Creates tmp directories for sessions, cache, sockets, and pids
```
