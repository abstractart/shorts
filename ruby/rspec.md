# Rspec useful tricks
## Mocks, Stubs
### Stubbing class which should instantiate in another (composition, has-a relationship)
```ruby
# Stubbing Openpay external service

# Stub instance of class
openpay = instance_double(OpenpayAdapter)
# stubbing constructor with double as return value
allow(OpenpayAdapter).to receive(:new).with(merchant_id, private_key)
                                      .and_return(openpay)

# stubbing instance method
allow(openpay).to receive(:create_charge).with(card_charge)
                                         .and_return(create_charge_result)
```


## Performance
### Disable logging
```ruby
# config/environments/test.rb
unless ENV['RAILS_ENABLE_TEST_LOG']
  config.logger = Logger.new(nil)
  config.log_level = :fatal
end
```

### Rspec with Spring binstub

```ruby
bundle exec spring binstub rspec
bin/rspec
```

NOTE: [simplecov](https://github.com/colszowka/simplecov) works not correct with this method

### Parallel tests
[Gem](https://github.com/grosser/parallel_tests)
