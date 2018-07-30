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
