# rosetta-checks

A suite of configuration files that allow us to validate the Rosetta implementation using rosetta-cli.

### Notes on `check:data`

 - `check:data` with historical balances lookup is supported, and it's the recommended method of validation.
 - `check:data` without historical balances (with _bootstrap balances_ instead) is supported, but is not recommended as a means of validation (hard to debug in case of reconciliation failures).

### Notes on `check:construction`

 - In the configuration of `check:construction`, make sure to set a large enough `"stale_depth"`, since the implementation only returns _final_ blocks (notarized by the Metachain and built upon), by default. There is a delay between the broadcast of the transaction and the moment at which the container block is marked as _final_. For example, use `"stale_depth": 10`.
 - In the construction DSL, `generate_account()` cannot be used, since it cannot be constrained to create accounts in the observed shard, at the moment. As a workaround, the accounts involved in a transfer (sender, recipient) should be explicitly specified in the `*.ros` file. 
