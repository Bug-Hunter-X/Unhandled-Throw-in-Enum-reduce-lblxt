# Elixir Enum.reduce Exception Handling

This example highlights a potential issue when using `throw` within Elixir's `Enum.reduce`.  The `throw` macro effectively halts the `reduce` operation, but there's no straightforward mechanism to catch the exception within the `reduce` function itself. This can lead to unexpected behavior and crashes.

The solution provided demonstrates a more robust approach using `try...catch` to handle the potential exception, allowing for more controlled error handling.

**Problem:**  The `throw` in the original `Enum.reduce` stops processing, offering no mechanism for recovery or alternative actions within the `reduce` context.

**Solution:**  The improved code wraps the `Enum.reduce` in a `try...catch` block.  This enables catching the `:three_found` exception and providing a graceful alternative (returning -1 in this example).