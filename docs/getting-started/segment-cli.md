# Segment CLI
Segment comes with a simple command line utility to interact with the segment server.

## Command Line Flags
By default `segment-cli` tries to connect to the segment server on `127.0.0.1:7890` but you can pass a host and a port using the `--port` and `--host` flags.

```bash
segment-cli --port=6969 --host=my.custom.host
```

## Using the CLI
Upon a successful connection you are presented with a prompt where you can execute commands. See [command reference](/getting-started/command-reference) for a full list of commands.
```bash
127.0.0.1:7890> 
```

## Examples

Create a new keyspace.
```bash
127.0.0.1:7890> CREATE tokens EV LRU
```

Insert a value into the keyspace.
```bash
127.0.0.1:7890> SET tokens foo bar
```

Get a value from the keyspace.
```bash
127.0.0.1:7890> GET tokens foo
```

Delete a value from the keyspace
```bash
127.0.0.1:7890> DEL tokens foo
```