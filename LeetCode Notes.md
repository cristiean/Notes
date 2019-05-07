# LeetCode Notes

Things that came up in LeetCode problems that I thought would be worth diving deeper into.

## [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

### Storage data structures and their lookup efficiencies

- `list()`
	- Stores values in a sequence
	- Lists are mutable
	- `append(object)` appends an `object` at the end of the list
	- `extend(list)` appends the elements of the `list` at the end of the method-calling list. The `+` operator can also be used. The `*` can ease the creation of lists with similar values (e.g. `[1, 2] * 2` will return `[1, 2, 1, 2]`)
	- `index(element, nth)` searches for an element in a list
	- `insert(index, element)`
	- `remove(element)`
	- `pop()` removes the last item of a list
	- `count(element)`
	- `sort()`
	- `reverse()` reverse in-place
	- To use lists as stacks (**LIFO**), use `append()` and `pop()`
	- To use lists as queues (**FIFO**), use `append()` and `pop(0)`
	- The `=` operator is a reference, not a copy
- Copy lists with `copy(list)` (shallow copy). Use `copy.deepcopy(list)` for deep copies. Remember to `import copy` first
- `tuple()`
	- Stores values in a sequence
	- Tuples are immutable. This makes tuple manipulations faster than that of a `list()`.
	- If you want to create a tuple with a single element, you must use the comma: `singleton = (1, )`
	- You can concatenate tuples by using the `+` operator
	- You can repeat tuples by using the `*` operator: `(1, ) * 5` returns `(1, 1, 1, 1, 1)
	- Tuples as `(key, value)` pairs to build dictionaries with. (`d = dict([('Mon', 1), ('Wed', 3)])`)
	- Signing multiple values: `(a, b, c) = (100, 20, 35)`
	- Tuple unpacking: `>>> data = (1, 2, 3)` -> `>>> x, y, z = data` -> `>>> x` returns `1`
	- Swap: `(x, y) = (y, x)`
	- Copying tuples can be done with the `=` operator, as they are immutable, and copying the reference is in order.
	- Warning! Tuples are not completely immutable. If a value within a tuple is mutable, then you can change it. (e.g. `>>> t = (1, 2, ['a', 'b'])` -> `>>> t[2].pop()` will return `'b'`. Also `>>> t` will return `(1, 2, ['a'])`
	- Convert tuple into a string using `str(t)` or `'t'`
- `set()`
	- Stores values unorderly. Sets are constructed from a sequence (or some other iterable object)
	- There are no multiple occurrences of the same element
	- Sets are mutable. A set is made up of (hashable) immutable objects.
	- Sets are highly efficient at removing duplicate values from a collection.
	- Sets offer set operations:
		- Union. `a | b` or `a.union(b)`
		- Intersection. `a & b` or `a.intersection(b)`
		- Difference. `a - b` or `a.difference(b)`
		- Symmetric Difference. `a ^ b` or `a.symmetric_difference(b)`
		- Is subset. `a <= b` or `a.issubset(b)`
		- Is superset. `a >= b` or `a.issuperset(b)`
- `frozenset()`
	-  Frozensets are immutable (hashable) sets
	-  If, however, you need nested sets, you can use `set(frozenset())`
- `dict()`
	- A sequence of items. Each item is a pair made of a key and a value. There cannot be duplicate items in a dictionary.
	- Dictionaries are not sorted. 
	- You can access the list of keys or values independently with `keys()` and `values()`
	- Access the value of a given key as follows: `>>> d[key]` will return the value associated with the `key`
	- `items()` returns the dictionary's items as a list of `(key, value)` items, with no particular order.
	- Check existence of a specific key with `d.has_key(key)`. Equivalent to `key in d`
	- `pop(key)` returns the item with key `key` and removes it from the dictionary
	- `popitem()` returns and removes an item `(key, value)`. You do not choose which one because a dictionary is not sorted.
	- Since dictionaries are objects, the `=` operator copies the reference, and not the content. For shallow copies use `copy(d)`, and for deep copies use `copy.deepcopy(d)`.
	- You can clear a dictionary (remove all its items) using the `clear()` method
	- The `delete(item)` method deletes just one item
	- If `key` is in a dictionary, `setdefault(key, default_value)` will return the value associated with it, otherwise it will return the `default_value` and add the `(key, default_value)` pair to the dictionary.
	- `get(key, a_value)` will return the value associated with the `key`, if `key` is in the dictionary, or `a_value` if `key` is not in the dictionary.
	- Combining dictionaries with `update(d)`. The items in the supplied dictionary are added to the old one, overwriting any items with the same keys.
	- `viewkeys()`, `viewvalues()`, `viewitems()` return set-like objects providing a view on the dictionary. (I have tested them, and they only seem to work with Python2 and not Python3 objects)

### Ternary operator
- The ternary operator `[on_true] if [expression] else [on_false]` can only be used with expressions, and not statements like `pass`, `continue`, `break` and so on.

---
## Resources
- [Python 2 Documentation](https://docs.python.org/2)
- [Python 3 Documentation](https://docs.python.org/3)
- [Python reference (The right way)](https://python-reference.readthedocs.io/en/latest/)
- [Thomas-Cokelaer - Python Notes](https://thomas-cokelaer.info/tutorials/python/)
