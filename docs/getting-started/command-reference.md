# Command Reference

## `CREATE`
The `CREATE` commnd is used to create a new keyspace. It accepts one optional argument `EV`. Here `EV` is the evictor, if you dont pass anything, by default `NOOP` evictor is chosen.

The `CREATE` command is idempotent, meaning that you can call the same command n-number of times and it will produce the same result.

### Return Type
The return type of the `CREATE` command is an integer. It returns `1` if a new keyspace was created and `0` if a new keyspace was not created beacuse one with a same name already exists.

If the command is malformed in any way, an error is returned.

### Examples

Create a keyspace named `tokens` with default config.
```bash
CREATE tokens
```

Create a keyspace named `tokens` with `LRU` evictor.
```bash
CREATE tokens EV LRU
```

Create a keyspace named `tokens` with `RANDOM` evictor.
```bash
CREATE tokens EV RANDOM
```

## `SET`
The `SET` commnd is used to insert a new key-value pair into a keyspace.

### Return Type
The return type of the `SET` command is an integer. It returns `1` if the key-value pair was inserted and `0` if it was not because of any reason.

If the command is malformed in any way, an error is returned.

### Examples

Insert key `foo` with value `bar` into a keyspace named `tokens`.
```bash
SET tokens foo bar
```

## `GET`
The `GET` command is used to get a value associated with a key.

### Return Type
The return type of the `GET` command is a `blob`. It returns the value if the key was found and `null` if it was not.

If the command is malformed in any way, an error is returned.

### Examples

Get the value for key `foo` in keyspace `tokens`.
```bash
GET tokens foo
```

## `DEL`
The `DEL` command is used to delete a key.

### Return Type
The return type of the `DEL` command is an integer. It returns `1` if the key was deleted and `0` if it was not because it didn't exist.

If the command is malformed in any way, an error is returned.

### Examples

Delete the key `foo` in keyspace `tokens`.
```bash
DEL tokens foo
```

## `DROP`
The `DROP` command is used to delete a keyspace.

### Return Type
The return type of the `DROP` command is an integer. It returns `1` if the keyspace was deleted and `0` if it was not because it didn't exist.

If the command is malformed in any way, an error is returned.

### Examples

Delete the keyspace `tokens`.
```bash
DROP tokens
```