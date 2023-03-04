# Redis 字符串(String)


|序号	|命令及描述|
| ---- | ------------------------------------------------------------ |
| 1    | SET key value 设置指定 key 的值。                            |
| 2    | GET key 获取指定 key 的值。                                  |
| 3    | GETRANGE key start end 返回 key 中字符串值的子字符           |
| 4    | GETSET key value 将给定 key 的值设为 value ，并返回 key 的旧值(old value)。 |
| 5    | GETBIT key offset 对 key 所储存的字符串值，获取指定偏移量上的位(bit)。 |
| 6    | MGET key1 [key2..\] 获取所有(一个或多个)给定 key 的值。      |
| 7    | SETBIT key offset value 对 key 所储存的字符串值，设置或清除指定偏移量上的位(bit)。 |
| 8    | SETEX key seconds value 将值 value 关联到 key ，并将 key 的过期时间设为 seconds (以秒为单位)。 |
| 9    | SETNX key value 只有在 key 不存在时设置 key 的值。           |
| 10   | SETRANGE key offset value 用 value 参数覆写给定 key 所储存的字符串值，从偏移量 offset 开始。 |
| 11   | STRLEN key 返回 key 所储存的字符串值的长度。                 |
| 12   | MSET key value [key value ...\] 同时设置一个或多个 key-value 对。 |
| 13   | MSETNX key value [key value ...\] 同时设置一个或多个 key-value 对，当且仅当所有给定 key 都不存在。 |
| 14   | PSETEX key milliseconds value 这个命令和 SETEX 命令相似，但它以毫秒为单位设置 key 的生存时间，而不是像 SETEX 命令那样，以秒为单位。 |
| 15   | INCR key 将 key 中储存的数字值增一。                         |
| 16   | INCRBY key increment 将 key 所储存的值加上给定的增量值（increment） 。 |
| 17   | INCRBYFLOAT key increment 将 key 所储存的值加上给定的浮点增量值（increment） 。 |
| 18   | DECR key 将 key 中储存的数字值减一。                         |
| 19   | DECRBY key decrement key 所储存的值减去给定的减量值（decrement） 。 |
| 20   | APPEND key value 如果 key 已经存在并且是一个字符串， APPEND 命令将指定的 value 追加到该 key 原来值（value）的末尾。 |

# Redis 哈希(Hash)

| 序号 | 命令及描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | HDEL key field1 [field2\] 删除一个或多个哈希表字段 |
| 2    | HEXISTS key field 查看哈希表 key 中，指定的字段是否存在。 |
| 3    | HGET key field 获取存储在哈希表中指定字段的值。 |
| 4    | HGETALL key 获取在哈希表中指定 key 的所有字段和值 |
| 5    | HINCRBY key field increment 为哈希表 key 中的指定字段的整数值加上增量 increment 。 |
| 6    | HINCRBYFLOAT key field increment 为哈希表 key 中的指定字段的浮点数值加上增量 increment 。 |
| 7    | HKEYS key 获取所有哈希表中的字段 |
| 8    | HLEN key 获取哈希表中字段的数量 |
| 9    | HMGET key field1 [field2\] 获取所有给定字段的值 |
| 10   | HMSET key field1 value1 [field2 value2 \] 同时将多个 field-value (域-值)对设置到哈希表 key 中。 |
| 11   | HSET key field value 将哈希表 key 中的字段 field 的值设为 value 。 |
| 12   | HSETNX key field value 只有在字段 field 不存在时，设置哈希表字段的值。 |
| 13   | HVALS key 获取哈希表中所有值。 |
| 14   | HSCAN key cursor [MATCH pattern\] [COUNT count] 迭代哈希表中的键值对。 |

# Redis 列表(List)

| 序号 | 命令及描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | BLPOP key1 [key2 \] timeout 移出并获取列表的第一个元素， 如果列表没有元素会阻塞列表直到等待超时或发现可弹出元素为止。 |
| 2    | BRPOP key1 [key2 \] timeout 移出并获取列表的最后一个元素， 如果列表没有元素会阻塞列表直到等待超时或发现可弹出元素为止。 |
| 3    | BRPOPLPUSH source destination timeout从列表中弹出一个值，将弹出的元素插入到另外一个列表中并返回它； 如果列表没有元素会阻塞列表直到等待超时或发现可弹出元素为止。 |
| 4    | LINDEX key index 通过索引获取列表中的元素                    |
| 5    | LINSERT key BEFORE\|AFTER pivot value 在列表的元素前或者后插入元素 |
| 6    | LLEN key 获取列表长度                                        |
| 7    | LPOP key 移出并获取列表的第一个元素                          |
| 8    | LPUSH key value1 value2 将一个或多个值插入到列表头部         |
| 9    | LPUSHX key value 将一个值插入到已存在的列表头部              |
| 10   | LRANGE key start stop 获取列表指定范围内的元素               |
| 11   | LREM key count value 移除列表元素                            |
| 12   | LSET key index value 通过索引设置列表元素的值                |
| 13   | LTRIM key start stop 对一个列表进行修剪(trim)，就是说，让列表只保留指定区间内的元素，不在指定区间之内的元素都将被删除。 |
| 14   | RPOP key 移除列表的最后一个元素，返回值为移除的元素。        |
| 15   | RPOPLPUSH source destination 移除列表的最后一个元素，并将该元素添加到另一个列表并返回 |
| 16   | [RPUSH key value1 value2] 在列表中添加一个或多个值到列表尾部 |
| 17   | RPUSHX key value 为已存在的列表添加值                        |

# Redis 集合(Set)

| 序号 | 命令及描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | [SADD key member1 member2] 向集合添加一个或多个成员          |
| 2    | SCARD key 获取集合的成员数                                   |
| 3    | [SDIFF key1 key2] 返回第一个集合与其他集合之间的差异。       |
| 4    | [SDIFFSTORE destination key1 key2] 返回给定所有集合的差集并存储在 destination 中 |
| 5    | [SINTER key1 key2] 返回给定所有集合的交集                    |
| 6    | [SINTERSTORE destination key1 key2] 返回给定所有集合的交集并存储在 destination 中 |
| 7    | SISMEMBER key member 判断 member 元素是否是集合 key 的成员   |
| 8    | SMEMBERS key 返回集合中的所有成员                            |
| 9    | SMOVE source destination member 将 member 元素从 source 集合移动到 destination 集合 |
| 10   | SPOP key 移除并返回集合中的一个随机元素                      |
| 11   | [SRANDMEMBER key count] 返回集合中一个或多个随机数           |
| 12   | [SREM key member1 member2] 移除集合中一个或多个成员          |
| 13   | [SUNION key1 key2] 返回所有给定集合的并集                    |
| 14   | [SUNIONSTORE destination key1 key2] 所有给定集合的并集存储在 destination 集合中 |
| 15   | SSCAN key cursor [MATCH pattern] [COUNT count] 迭代集合中的元素 |

# Redis 有序集合(sorted set)

| 序号 | 命令及描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | [ZADD key score1 member1 score2 member2] 向有序集合添加一个或多个成员，或者更新已存在成员的分数 |
| 2    | ZCARD key 获取有序集合的成员数                               |
| 3    | ZCOUNT key min max 计算在有序集合中指定区间分数的成员数      |
| 4    | ZINCRBY key increment member 有序集合中对指定成员的分数加上增量 increment |
| 5    | [ZINTERSTORE destination numkeys key key ...] 计算给定的一个或多个有序集的交集并将结果集存储在新的有序集合 destination 中 |
| 6    | ZLEXCOUNT key min max 在有序集合中计算指定字典区间内成员数量 |
| 7    | [ZRANGE key start stop WITHSCORES] 通过索引区间返回有序集合指定区间内的成员 |
| 8    | [ZRANGEBYLEX key min max LIMIT offset count] 通过字典区间返回有序集合的成员 |
| 9    | ZRANGEBYSCORE key min max [WITHSCORES] [LIMIT] 通过分数返回有序集合指定区间内的成员 |
| 10   | ZRANK key member 返回有序集合中指定成员的索引                |
| 11   | [ZREM key member member ...] 移除有序集合中的一个或多个成员  |
| 12   | ZREMRANGEBYLEX key min max 移除有序集合中给定的字典区间的所有成员 |
| 13   | ZREMRANGEBYRANK key start stop 移除有序集合中给定的排名区间的所有成员 |
| 14   | ZREMRANGEBYSCORE key min max 移除有序集合中给定的分数区间的所有成员 |
| 15   | [ZREVRANGE key start stop WITHSCORES] 返回有序集中指定区间内的成员，通过索引，分数从高到低 |
| 16   | [ZREVRANGEBYSCORE key max min WITHSCORES] 返回有序集中指定分数区间内的成员，分数从高到低排序 |
| 17   | ZREVRANK key member 返回有序集合中指定成员的排名，有序集成员按分数值递减(从大到小)排序 |
| 18   | ZSCORE key member 返回有序集中，成员的分数值                 |
| 19   | [ZUNIONSTORE destination numkeys key key ...] 计算给定的一个或多个有序集的并集，并存储在新的 key 中 |
| 20   | ZSCAN key cursor [MATCH pattern] [COUNT count] 迭代有序集合中的元素（包括元素成员和元素分值） |

# Redis HyperLogLog

| 序号 | 命令及描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | [PFADD key element element ...] 添加指定元素到 HyperLogLog 中。 |
| 2    | [PFCOUNT key key ...] 返回给定 HyperLogLog 的基数估算值。    |
| 3    | [PFMERGE destkey sourcekey sourcekey ...] 将多个 HyperLogLog 合并为一个 HyperLogLog |

# **命令行操作**

```shell
127.0.0.1:6379> set var1 abc
OK
127.0.0.1:6379> get var1
"abc"
127.0.0.1:6379> getrange var 0 1
""
127.0.0.1:6379> getrange var1 0 1
"ab"
127.0.0.1:6379> getset var1 456
"abc"
127.0.0.1:6379> getbit var1 1
(integer) 0
127.0.0.1:6379> set var2 222
OK
127.0.0.1:6379> mget var1 var2
1) "456"
2) "222"
127.0.0.1:6379> setbit var1 1 1
(integer) 0
127.0.0.1:6379> get var1
"t56"
127.0.0.1:6379> setex var3 10 20
OK
127.0.0.1:6379> get var3
"20"
127.0.0.1:6379> get var3
(nil)
127.0.0.1:6379> setnx var3 10
(integer) 1
127.0.0.1:6379> get var3
"10"
127.0.0.1:6379> setnx var3 20
(integer) 0
127.0.0.1:6379> get var3
"10"
127.0.0.1:6379> set var4 abcdefg
OK
127.0.0.1:6379> setrange var4 3 1234
(integer) 7
127.0.0.1:6379> get var4
"abc1234"
127.0.0.1:6379> STRLEN var4
(integer) 7
127.0.0.1:6379> mset var5 6 var6 7 var7 8
OK
127.0.0.1:6379> mget var5 var6 var7
1) "6"
2) "7"
3) "8"
127.0.0.1:6379> msetnx var5 6 var6 7 var7 8
(integer) 0
127.0.0.1:6379> mget var5 var6 var7
1) "6"
2) "7"
3) "8"
127.0.0.1:6379> psetex var8 10000 20
OK
127.0.0.1:6379> get var8
"20"
127.0.0.1:6379> get var8
(nil)
127.0.0.1:6379> set var8 10
OK
127.0.0.1:6379> incr var8
(integer) 11
127.0.0.1:6379> set var9 a
OK
127.0.0.1:6379> incr var9
(error) ERR value is not an integer or out of range
127.0.0.1:6379> incrby var8 10
(integer) 21
127.0.0.1:6379> INCRBYFLOAT var8 1.1
"22.1"
127.0.0.1:6379> set var 1 
OK
127.0.0.1:6379> decr var1
(integer) 0
127.0.0.1:6379> DECRBY var 20
(integer) -19
127.0.0.1:6379> append var1 aa
(integer) 3
127.0.0.1:6379> get var1
"0aa"
127.0.0.1:6379> hmset p1 name laowang age 10
OK
127.0.0.1:6379> HEXISTS p1
(error) ERR wrong number of arguments for 'hexists' command
127.0.0.1:6379> HEXISTS p1 name
(integer) 1
127.0.0.1:6379> HEXISTS p1 weight
(integer) 0
127.0.0.1:6379> hget p1 name
"laowang"
127.0.0.1:6379> hgetall p1
1) "name"
2) "laowang"
3) "age"
4) "10"
127.0.0.1:6379> hkeys p1
1) "name"
2) "age"
127.0.0.1:6379> hlen p1
(integer) 2
127.0.0.1:6379> hmget p1 name age
1) "laowang"
2) "10"
127.0.0.1:6379> hset p1 weight 250
(integer) 1
127.0.0.1:6379> hset p1 weight 200
(integer) 0
127.0.0.1:6379> hsetnx p1 weight 200
(integer) 0
127.0.0.1:6379> hget p1 weight
"200"
127.0.0.1:6379> hvals p1
1) "laowang"
2) "10"
3) "200"
127.0.0.1:6379> hscan p1 1
1) "0"
2) 1) "name"
   2) "laowang"
   3) "age"
   4) "10"
   5) "weight"
   6) "200"
127.0.0.1:6379> hdel p1 name
(integer) 1
127.0.0.1:6379> HEXISTS p1 name
(integer) 0
127.0.0.1:6379> LPUSH l1 a
(integer) 1
127.0.0.1:6379> LPUSH l1 b
(integer) 2
127.0.0.1:6379> LLEN l1
(integer) 2
127.0.0.1:6379> LINDEX l1 0
"b"
127.0.0.1:6379> LINDEX l1 1
"a"
127.0.0.1:6379> LINDEX l1 2
(nil)
127.0.0.1:6379> LINSERT l1 before 0 1
(integer) -1
127.0.0.1:6379> LLEN l1
(integer) 2
127.0.0.1:6379> LINDEX l1 0
"b"
127.0.0.1:6379> lpop l1
"b"
127.0.0.1:6379> lpop l1
"a"
127.0.0.1:6379> lpop l1
(nil)
127.0.0.1:6379> lpop l1
(nil)
127.0.0.1:6379> LPUSH a
(error) ERR wrong number of arguments for 'lpush' command
127.0.0.1:6379> LPUSH l1 a
(integer) 1
127.0.0.1:6379> LPUSH l1 b
(integer) 2
127.0.0.1:6379> LPUSH l1 c
(integer) 3
127.0.0.1:6379> RPOP l1
"a"
127.0.0.1:6379> RPOP l1
"b"
127.0.0.1:6379> RPOP l1
"c"
127.0.0.1:6379> RPOP l1
(nil)
127.0.0.1:6379> LPUSH l1 a
(integer) 1
127.0.0.1:6379> LPUSH l1 b
(integer) 2
127.0.0.1:6379> LPUSH l1 c
(integer) 3
127.0.0.1:6379> LSET l1 0 g
OK
127.0.0.1:6379> lindex l1 0
"g"
127.0.0.1:6379> RPUSH l1 j
(integer) 4
127.0.0.1:6379> RPUSH l1 k
(integer) 5
127.0.0.1:6379> RPUSH l1 l
(integer) 6
127.0.0.1:6379> lrange l1 0 6
1) "g"
2) "b"
3) "a"
4) "j"
5) "k"
6) "l"
127.0.0.1:6379> lrange l1 0 9
1) "g"
2) "b"
3) "a"
4) "j"
5) "k"
6) "l"
127.0.0.1:6379> lrange l1 0 
(error) ERR wrong number of arguments for 'lrange' command
127.0.0.1:6379> ltrim l1 0 3
OK
127.0.0.1:6379> lrange l1 0 10
1) "g"
2) "b"
3) "a"
4) "j"
127.0.0.1:6379> llen l1
(integer) 4
127.0.0.1:6379> blpop l1 10
1) "l1"
2) "g"
127.0.0.1:6379> sadd s1 a b c d
(integer) 4
127.0.0.1:6379> SCARD s1
(integer) 4
127.0.0.1:6379> sadd s2 b c d
(integer) 3
127.0.0.1:6379> sdiff s1 s2
1) "a"
127.0.0.1:6379> sdiff s2 s1
(empty list or set)
127.0.0.1:6379> sdiffstore s3 s1 s2
(integer) 1
127.0.0.1:6379> scard s3
(integer) 1
127.0.0.1:6379> smembers s3
1) "a"
127.0.0.1:6379> sinter s1 s2
1) "d"
2) "c"
3) "b"
127.0.0.1:6379> sinterstore s4 s1 s2
(integer) 3
127.0.0.1:6379> smembers s4
1) "c"
2) "d"
3) "b"
127.0.0.1:6379> smembers s1
1) "d"
2) "c"
3) "b"
4) "a"
127.0.0.1:6379> smembers s2
1) "d"
2) "c"
3) "b"
127.0.0.1:6379> smove s1 s2
(error) ERR wrong number of arguments for 'smove' command
127.0.0.1:6379> smove s1 s2 a
(integer) 1
127.0.0.1:6379> smember s1
(error) ERR unknown command 'smember'
127.0.0.1:6379> smembers s1
1) "d"
2) "c"
3) "b"
127.0.0.1:6379> smembers s2
1) "d"
2) "c"
3) "a"
4) "b"
127.0.0.1:6379> spop s1
"d"
127.0.0.1:6379> smembers s1
1) "c"
2) "b"
127.0.0.1:6379> srandmember s2 2
1) "d"
2) "a"
127.0.0.1:6379> srandmember s2 1
1) "b"
127.0.0.1:6379> srandmember s2 1
1) "b"
127.0.0.1:6379> srandmember s2 1
1) "a"
127.0.0.1:6379> sunion s1 s2
1) "d"
2) "c"
3) "a"
4) "b"
127.0.0.1:6379> zadd z1 1 one
(integer) 1
127.0.0.1:6379> zadd z1 1 two
(integer) 1
127.0.0.1:6379> zadd z1 2 three
(integer) 1
127.0.0.1:6379> zrange z1 0 -1
1) "one"
2) "two"
3) "three"
127.0.0.1:6379> zrange z1 0 -1 withscores
1) "one"
2) "1"
3) "two"
4) "1"
5) "three"
6) "2"
127.0.0.1:6379> zcard z1
(integer) 3
127.0.0.1:6379> zcount z1 0 2
(integer) 3
127.0.0.1:6379> zcount z1 0 1
(integer) 2
```

