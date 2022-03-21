# Migrate from a split markets process to Boost

If you are running markets as a separate lotus-miner instance (MRA), use `boost migrate` instead of `boost init`:

```
boost --vv migrate \
      --import-markets-repo=~/.my-markets-repo \
      --wallet-publish-storage-deals=$PUBLISH_STORAGE_DEALS_WALLET \
      --wallet-collateral-pledge=$PLEDGE_COLLAT_WALLET \
      --max-staging-deals-bytes=50000000000
```

The migrate command

* Initializes a Boost repository
* Migrates markets datastore keys to Boost
  * Storage and retrieval deal metadata
  * Storage and retrieval ask data
* Migrates markets libp2p keys to Boost
* Migrates markets config to Boost (libp2p endpoints, settings etc)
* Migrates the markets DAG store to Boost