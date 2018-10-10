### connection_pool
---

https://github.com/mperham/connection_pool

```ruby
$memcached = ConnectionPool.new(size: 5, timeout: 5) { Dalli::Client.new }

$memcached.with do |conn|
  conn.get('some-count')
end

$memcached.with(timeout: 2.0) do |conn|
  conn.get('some-count')
end

$redis = ConnectionPool::Wrapper.new(size: 5, timeout: 3) { Redis.connect }
$redis.sadd('foo', 1)
$redis.smembers('foo')

$redis.with do |conn|
  conn.sadd('foo', 1)
  conn.smembers('foo')
end

cp = ConnectionPool.new(size: 10) { Redis.new }
cp .shutdown { |conn| conn.quit }

cp = ConnectionPool.new(size: 10) { Redis.new }
cp.size
cp.available

cp.with do |conn|
  cp.size
  cp.available
end



```


```

```

