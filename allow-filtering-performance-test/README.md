# Requirements

- java 1.8
- [berserker-runner.jar](https://bintray.com/smartcat-labs/maven/berserker#files/io%2Fsmartcat%2Fberserker-runner)

# How to run yourself

`java -jar berserker-runner-0.0.8.jar -c config-file | tee results.log`

# Config files

- `config-allow-filtering` - config file for running queries with `allow filtering`: `"SELECT * FROM users_by_tag WHERE tag = '{}' AND age > 35 ALLOW FILTERING;", $tag`.
- `config-no-allow-filtering` - config file for runnig queries without `allow filtering` - `"SELECT * FROM users_by_tag WHERE tag = '{}';", $tag`

Consistency level in configuration files can be changed by `consistencyLevel` property (inside of `data-source-configuration.values.statement`).

# Log Files - Results

- `allow-filtering-one.log` - contains logged results for running 10k requests with this query: `"SELECT * FROM users_by_tag WHERE tag = '{}' AND age > 35 ALLOW FILTERING;", $tag` with consistency level ONE.
- `allow-filtering-quorum.log` - contains logged results for running 10k requests with this query: `"SELECT * FROM users_by_tag WHERE tag = '{}' AND age > 35 ALLOW FILTERING;", $tag` with consistency level QUORUM.
- `no-allow-filtering-one.log` - contains logged results for running 10k requests with this query: `"SELECT * FROM users_by_tag WHERE tag = '{}';"` with consistency level ONE.
- `no-allow-filtering-quorum.log` - contains logged results for running 10k requests with this query: `"SELECT * FROM users_by_tag WHERE tag = '{}';"` with consistency level QUORUM.
