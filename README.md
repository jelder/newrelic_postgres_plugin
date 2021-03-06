NewRelic Postgres Plugin
========================

A NewRelic Platform Postgres Plugin

The New Relic Postgres Plugin enables integrated monitoring of your Postgres database in a custom NewRelic dashboard. Currently the following metrics are recorded:

* Index size, miss rate, and count
* Cache miss rate
* Idle and active connection counts
* BGWriter metrics
* Tuple metrics
* Transactions committed and rolled back

## Requirements

### Proxy host

You need a host to install the plugin on that is able to poll the desired Postgres database. That
host also needs Ruby (tested with 2.0.0), and support for rubygems. Heroku is a great choice for this. A fully deployable example app is provided.

https://github.com/GoBoundless/heroku_postgres_monitor

### Postgres

This plugin has been tested with with a few different Postgres version and should work with any version compatible with the pg gem.

## Installation and Running

1. Install this gem from RubyGems:

      ```gem install newrelic_postgres_plugin```

2. Create an installation directory (like /opt/newrelic/postgres ).
3. In the installation directory, execute

      ```pg_monitor install -l LICENSE_KEY```

   using the license key from your New Relic account.
4. Edit the `config/newrelic_plugin.yml` file generated in step 4. Setup host/port/user/password/dbname for your postgres connection.
5. Execute

      ```pg_monitor run```

6. You should now see your results in the left-hand navigation of the NewRelic web UI under a tab labeled 'Postgres'.

## Heroku Instructions

Unlike the default NewRelic Postgres plugin, this plugin is designed to be fully compatible with monitoring Heroku Postgres. In fact, we've even created a simple app you can run on Heroku to monitor your existing apps.

Instructions for using Heroku as your proxy host can be found in the [heroku_postgres_monitor](https://github.com/GoBoundless/heroku_postgres_monitor) repo.

## Support

Please use Github issue for support. We will do our best to address issues in a timely fashion.

## Developer Instructions

1. Fork/Clone the repository
2. Install bundler and run:

      ```bundle install```

3. Run `rake -T` to see rake options, including tests.
