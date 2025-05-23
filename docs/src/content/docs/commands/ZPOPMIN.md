---
title: ZPOPMIN
description: ZPOPMIN removes and returns the member with the lowest score from the sorted set at the specified key.
---

<!-- This file is automatically generated. Any modifications made directly to this file
  may be overwritten. For more details on how this file is generated and how to use
  the related commands, refer to the documentation available in the `internal/cmd/cmd_*.go` files.
-->

#### Syntax

```
ZPOPMIN key [count]
```


ZPOPMIN removes and returns the member with the lowest score from the sorted set at the specified key.

If the key does not exist, the command returns empty list. An optional "count" argument can be provided
to remove and return multiple members (up to the number specified).
	

#### Examples

```

localhost:7379> ZADD users 1 alice
OK 1
localhost:7379> ZADD users 2 bob
OK 1
localhost:7379> ZADD users 3 charlie
OK 1
localhost:7379> ZPOPMIN users
OK
0) 1, alice
localhost:7379> ZPOPMIN users 10
OK
0) 2, bob
1) 3, charlie
	
```
