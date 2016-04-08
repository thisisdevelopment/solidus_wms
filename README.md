SolidusWms
==========

[![Build Status](https://travis-ci.org/madetech/solidus_wms.svg?branch=master)](https://travis-ci.org/madetech/solidus_wms)

Adds additional API endpoints, and state machine events to the `Spree::Shipment` to provide an integration with your WMS of choice.

Installation
------------

Add solidus_wms to your Gemfile:

```ruby
gem 'solidus_wms'
```

Bundle your dependencies and run the installation generator:

```shell
bundle
bundle exec rails g solidus_wms:install
```

Testing
-------

First bundle your dependencies, then run `rake`. `rake` will default to building the dummy app if it does not exist, then it will run specs, and [Rubocop](https://github.com/bbatsov/rubocop) static code analysis. The dummy app can be regenerated by using `rake test_app`.

```shell
bundle
bundle exec rake
```

When testing your applications integration with this extension you may use it's factories.
Simply add this require statement to your spec_helper:

```ruby
require 'solidus_wms/factories'
```

Endpoints
---------

`/api/shipments/:id/receive` Moves a Shipment from `ready` to `recieved`
`/api/shipments/:id/pick` Moves a Shipment from `received` to `picked`

`/api/orders/:id/export` Marks an order as exported, by touching the `exported_at`
`/api/order/to_export` Lists all orders ready to export before a provided timestamp



Copyright (c) 2016 Seb Ashton and [Made Tech](https://www.madetech.com) released under the New BSD License
