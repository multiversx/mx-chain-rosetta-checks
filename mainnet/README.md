## Run the checks

Set the Rosetta URLs:

```
export ROSETTA_ONLINE=http://localhost:8091
export ROSETTA_OFFLINE=http://localhost:8092
```

Check the data API using historical balances:

```
rosetta-cli check:data --configuration-file mainnet-data-historical.json \
--online-url=${ROSETTA_ONLINE} --data-dir=mainnet-historical
```
