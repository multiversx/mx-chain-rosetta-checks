## Run the checks

Set the Rosetta URLs:

```
export ROSETTA_ONLINE=http://localhost:7091
export ROSETTA_OFFLINE=http://localhost:7092
```

### Construction API

Using `operations` without `metadata` - only suitable for transfers among accounts within the _observed projected shard_:

```
rosetta-cli check:construction --configuration-file devnet-construction.json \
--online-url=${ROSETTA_ONLINE} --offline-url=${ROSETTA_OFFLINE}
```

Using an `operation` (for _sender_) and `metadata` (for _receiver_) - suitable for transfers where the _sender_ is located in the _observed projected shard_, while the _receiver_ can be located in any shard:

```
rosetta-cli check:construction --configuration-file devnet-construction-with-metadata.json \
--online-url=${ROSETTA_ONLINE} --offline-url=${ROSETTA_OFFLINE}
```

### Data API

Check the data API using historical balances:

```
rosetta-cli check:data --configuration-file devnet-data-historical.json \
--online-url=${ROSETTA_ONLINE} --data-dir=devnet-historical
```
