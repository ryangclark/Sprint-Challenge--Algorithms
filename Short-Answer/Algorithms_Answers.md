## Exercise I

a) `O(n)`
   This one caught me up for a second! That's fun.
   The `a = a + n * n` is O(1) time complexity. But because it impacts the conditions of the `while` loop, it's quite important. The `n * n` within the loop cancels out an equivalent `n * n` in the `while` condition, leaving only `a < n`, which means the complexity is `O(n)`.

b) `O(n^3)`
   I'm not too confident in this analysis. The outermost loop has complexity of `O(n)`, then the next two inner loops are also of `O(n)` complexity because they rely on `n`, even though they are slightly smaller than `n` with the adding functionality. The third loop, `for l in range(k + 1, 10 + k):` relies upon `n` as well in a disconnected way, but it is inherently limited by the upper bound to be 9, so it's `O(1)`.

c) `O(n)`
   Written as a `for` loop, this would be `2 + i for i in bunnies`

## Exercise II

This is a great candidate for binary search.
Something like this could get you started:
```
def find_floor(num_floors):
	high = num_floors
	mid = num_floors // 2
	low = 0

	while True:
		if high - low == 1:
			break # lol
		if broken_egg:
			high = mid
			mid = (high + low) // 2
		if unbroken_egg:
			low = mid
			mid = (high + low) // 2
	return mid
			
```
That would allow you to quickly find where the eggs begin breaking. But that's not a solution. We need to find the _lowest_ floor.

Once we have a broken egg, we need to look at the lower floors – we can safely ignored any higher floors because they'll all break an egg.