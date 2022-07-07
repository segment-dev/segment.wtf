---
sidebar_position: 2
---

# Segment Server
The `segment-server` binary starts the Segment server. By default it runs on port `7890` but that can be changed by providing command line flags or by changing the server port in `segment.conf.json`.

## The Config File
`segment-server` comes with `segment.conf.json` which has the following structure.

```json
{
  "port": 7890,
  "max_memory": 1024
}
```

- `port` is the server port.
- `max_memory` is the max memory server is able to use in **megabytes**.

## Command Line Flags

You can specify the location of the config file if it's not in the same directory as the binary by passing the `--config` flag.
```bash
segment-server --config=/path/to/segment.conf.json
```

You can override the server port in `segment.conf.json` by passing the `--port` flag.
```bash
segment-server --port=6969
```

You can also override `max_memory` in `segment.conf.json` by passing the `--max_memory` flag.
```bash
segment-server --max_memory=4096
```

## Keyspaces
Segment has keyspaces, which are like tables in a relational database. You can create as many keyspaces as you like. For example let's say you are building an authenication system you can create one keyspace for auth tokens and one for user data and one for some other data, you get the point. Keyspaces should store data of similar type.

:::info
Keyspaces are not permanent, they are dropped when the server shuts down.
:::

## Evictors
Each keyspace has an evictor associated with it, which kicks in when the server reaches the memory limit specified by `max_memory` in `segment.conf.json`. Currently there are 3 types of evictors supported by the Segment server namely, `LRU`, `RANDOM` and `NOOP`. Let's go over them one by one.

### LRU Evictor
The LRU evictor evicts keys in an lru fashion which means that the key with the oldest access time will be removed first.

### Random Evictor
As the name suggests, the Random evictor evicts key in a random order.

### NOOP Evictor
NOOP here means no operation, which means that this evictor does not evict at all. This is the default evictor if none is provided at the time of keyspace creation.
