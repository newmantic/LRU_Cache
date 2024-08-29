# LRU_Cache


An LRU (Least Recently Used) cache is a data structure that stores a limited number of items, where the least recently accessed items are discarded when the cache reaches its capacity. The primary goal of an LRU cache is to keep the most recently used data in memory to optimize access time for frequently used items.


The cache has a fixed size, denoted as C.
When the cache is full (contains C items), adding a new item requires removing the least recently used item.
Operations:

Get(key):
If the item with the given key is in the cache, return its value.
If the item is not in the cache, return -1.
Accessing an item makes it the most recently used, so it should be moved to the front of the cache.

Put(key, value):
If the item with the given key is already in the cache, update its value and move it to the front.
If the item is not in the cache, insert it. If the cache is full, remove the least recently used item before inserting the new one.


Cache State:
Represent the cache as an ordered sequence of key-value pairs: [(k_1, v_1), (k_2, v_2), ..., (k_n, v_n)]
k_i represents a key, and v_i represents the corresponding value.
The order of elements in the sequence indicates the recency of use: k_1 is the most recently used, and k_n is the least recently used.

Get Operation:
If the key exists in the cache:
Let the key be k_x with corresponding value v_x.
Move (k_x, v_x) to the front of the sequence.
Return v_x.
If the key does not exist, return -1.

Put Operation:
If the key already exists:
Let the key be k_x with value v_x.
Update v_x to the new value and move (k_x, v_x) to the front of the sequence.
If the key does not exist:
Insert (k, value) at the front of the sequence.

If the cache size exceeds C:
Remove the item at the end of the sequence (the least recently used item).
