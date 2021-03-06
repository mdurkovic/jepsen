# Jepsen Dgraph Tests

A test suite for the Dgraph distributed graph database.

## Usage

`lein test` runs tests; use `lein test --help` for details. For instance:

```
lein run test --local-binary ~/tmp/dgraph --nemesis none --rebalance-interval 10h --sequencing server --upsert-schema --time-limit 600 --concurrency 1n --workload bank --retry-db-setup --test-count 20
```

... tests a local binary in ~/tmp/dgraph, with network partitions, automatically rebalancing every 10 hours, using server-side sequencing, @upsert schema directives, with tests lasting 600 seconds, one client per node, performing the `bank` test workload, working around database join issues in dgraph, and for 20 tests, or until one test fails.

Use `lein run test-all` to run a full test suite. Test-all takes many of the
same arguments as `test`, but cycles through all combinations of workload,
nemesis, sequencing, and upserts.

## License

Copyright © 2018 Jepsen, LLC

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
