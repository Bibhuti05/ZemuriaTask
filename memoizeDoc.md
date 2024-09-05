## Memoization Example

This code demonstrates a memoization technique using JavaScript closures. Memoization is an optimization technique that involves caching the results of expensive function calls and returning the cached result when the same inputs occur again.

### `memoize` Function

The `memoize` function takes a function `fn` as an argument and returns a new function that wraps the original function. The returned function uses a cache to store the results of previous function calls.

1. A `Map` object called `cache` is created to store the cached results.
2. The returned function uses the spread operator (`...`) to accept any number of arguments passed to it.
3. The arguments are converted to a string using `JSON.stringify` to create a unique key for the cache.
4. If the key exists in the cache, the cached result is returned, and a message is logged to the console indicating that the result is being fetched from the cache.
5. If the key does not exist in the cache, the original function `fn` is called with the provided arguments, and the result is stored in the cache using the key.
6. The result is returned, and a message is logged to the console indicating that the result is being calculated.

### `factorial` Function

The `factorial` function is defined using the `memoize` function. It calculates the factorial of a given number `n` recursively.

1. If `n` is less than or equal to 1, the function returns 1.
2. Otherwise, the function returns `n` multiplied by the factorial of `n - 1`.

### Example Usage

1. The factorial of 10 is calculated using the `factorial` function and the result is logged to the console.
2. The factorial of 4 is calculated using the `factorial` function and the result is logged to the console.

When running the code, you should see the following output:
