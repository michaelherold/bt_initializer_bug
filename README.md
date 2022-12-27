# Bridgetown initializer bug repository

This repository demonstrates a bug in Bridgetown 1.2.0.beta4 where initializers do not allow the `url` property to change in development mode.

When using `bridgetown.config.yml` to set the `url` property, Bridgetown is able to override the value when doing local development. 

## Instructions

1. Run `bin/setup` to install dependencies
2. Run `bin/bt dev` to start the development server
3. Navigate to `https://localhost:4000` and see that the URL for the site is `https://localhost:4000` on the page and the absolute URL for the page is `https://localhost:4000/`
4. Stop the server
5. Uncomment `config/initializers.rb:2`
6. Run `bin/bt dev` to start the development server
7. Navigate to `https://localhost:4000` and **see that the URL for the site is now `https://example.com` on the page** and **the absolute URL for the page is `https://localhost:4000/`**
8. Compare `bridgetown.config.yml` and `config/initializers.rb` to see that they are configured the same

## Files of interest

Most of the files in this repository are boilerplate. The only ones of interest are:

1. `bridgetown.config.yml`
2. `config/initializers.rb`
3. `src/index.md`
