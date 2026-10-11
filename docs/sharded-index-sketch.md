# Sharded index sketch

The index is one in-memory structure today. Sharding by hash prefix onto
disk would keep scans memory-flat, with each shard loaded per query range.

Open question: whether shard files stay content-addressed like the rest of
the tool, or get their own format. Both keep scans deterministic.
