# `in_batches`

There are a few protips when using `in_batches`.

## Selects only record ids

```ruby
User.in_batches(of: 1000) do |batch|
  puts "Processing batch of #{batch.size} users"
end
```

:bulb: `in_batches` will automatically use `.select(:id)` to fetch the batch of record ids instead of fetching the entire record. This improves performance and memory usage.

This means that `User.select(:id).in_batches(of: 1000)` is unnecessary.

## Perform an action on each batch

```ruby
User.in_batches(of: 1000).destroy_all
```

vs.

```ruby
User.in_batches(of: 1000, &:destroy_all)
```

:bulb: You can pass a block to `in_batches` to perform an action on each batch. The former will generate a single SQL query to fetch all the ids and then iterate over each batch. The latter will generate a single SQL query per batch.

:tada: Happy coding!
