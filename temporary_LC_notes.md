# `string()`
	- `find(sub, start, end)` returns the lowest index where `sub` is found in the string such that it is fully contained within `string[start:end]`. Returns `-1` on failure.
	- `index(sub, start, end)` like `find()` but raise `ValueError` when substring is not found
	- `rfind(sub, start, end)` performs the same operation as `find()` but returns the highest index found
	- `rindex(sub, start, end)` like `index()` but returns the highest index

# Sliding Window approach:
	- Useful for string (substring) or array (subarray) -based problems.
	- Can turn a nested-loop solution (usually brute force) into a single loop solution.
	- Can cut complexity from __quadratic__ to __linear__. (for example, if you have to find the subarray of size `k` with the highest sum, instead of checking all subarrays of size `k`, you can just move the indices forward and graze over the input linearly).
	- Makes use of two indices _begin_ and _end_ that represent the limits of the window.

# Maximum constant:
	- `sys.maxint` constant has been removed from Python 3 onwards.
	- use the `sys.maxsize` constant instead. This is a positive integer that is practically larger than any string or list index.
 
