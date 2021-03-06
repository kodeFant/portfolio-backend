# WordPress Backend for lillo.tech

I use this WordPress install to serve images and data to my Gatsby site with the use of WordPress Rest API.

## Requirements

- PHP >= 5.6
- Composer - [Install](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)

## Installation

1. Create a new project in a new folder for your project:

`composer create-project roots/bedrock your-project-folder-name`

2. Update environment variables in `.env` file:

- `DB_NAME` - Database name
- `DB_USER` - Database user
- `DB_PASSWORD` - Database password
- `DB_HOST` - Database host
- `WP_ENV` - Set to environment (`development`, `staging`, `production`)
- `WP_HOME` - Full URL to WordPress home (http://example.com)
- `WP_SITEURL` - Full URL to WordPress including subdirectory (http://example.com/wp)
- `AUTH_KEY`, `SECURE_AUTH_KEY`, `LOGGED_IN_KEY`, `NONCE_KEY`, `AUTH_SALT`, `SECURE_AUTH_SALT`, `LOGGED_IN_SALT`, `NONCE_SALT`

If you want to automatically generate the security keys (assuming you have wp-cli installed locally) you can use the very handy [wp-cli-dotenv-command][wp-cli-dotenv]:

      wp package install aaemnnosttv/wp-cli-dotenv-command

      wp dotenv salts regenerate

Or, you can cut and paste from the [Roots WordPress Salt Generator][roots-wp-salt].

3. Add theme(s) in `web/app/themes` as you would for a normal WordPress site.

4. Set your site vhost document root to `/path/to/site/web/` (`/path/to/site/current/web/` if using deploys)

5. Access WP admin at `http://example.com/wp/wp-admin`

## Deploys

There are two methods to deploy Bedrock sites out of the box:

- [Trellis](https://github.com/roots/trellis)
- [bedrock-capistrano](https://github.com/roots/bedrock-capistrano)

Any other deployment method can be used as well with one requirement:

`composer install` must be run as part of the deploy process.

## Documentation

Bedrock documentation is available at [https://roots.io/bedrock/docs/](https://roots.io/bedrock/docs/).

## Contributing

Contributions are welcome from everyone. We have [contributing guidelines](https://github.com/roots/guidelines/blob/master/CONTRIBUTING.md) to help you get started.

## Community

Keep track of development and community news.

- Participate on the [Roots Discourse](https://discourse.roots.io/)
- Follow [@rootswp on Twitter](https://twitter.com/rootswp)
- Read and subscribe to the [Roots Blog](https://roots.io/blog/)
- Subscribe to the [Roots Newsletter](https://roots.io/subscribe/)
- Listen to the [Roots Radio podcast](https://roots.io/podcast/)

[roots-wp-salt]: https://roots.io/salts.html
[wp-cli-dotenv]: https://github.com/aaemnnosttv/wp-cli-dotenv-command
