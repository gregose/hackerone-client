# Hackerone::Client

A limited client library for interacting with HackerOne. Currently only supports two endpoints:

* `/reports` returns all reports in the "new" state for a given program
* `/report/{id}` returns report data for a given report

## Usage

### Credential management

You'll need to generate an API token at https://hackerone.com/&lt;program&gt;/api.

* Click "Create API token"
* Name the token
* Click "Create"
* Copy down the value

Set the `HACKERONE_TOKEN` and `HACKERONE_TOKEN_NAME` environment variables.

### Program name

In order to retrieve all reports for a given program, you need to supply a default program:

```ruby
HackerOne::Client.program = "github"
```

### Risk classification

Configure the low/med/high/crit ranges for easier classification based on payouts:

```ruby
HackerOne::Client.low_range = 1..999
HackerOne::Client.medium_range = 1000...2500
HackerOne::Client.high_range = 2500...5000
HackerOne::Client.critical_range = 5000...100_000_000
```

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/oreoshake/hackerone-client. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
