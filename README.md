# Lua Nested Table Iteration Bug

This repository demonstrates a subtle bug related to iterating over nested tables in Lua using the `pairs` function.  The issue arises when modifying a table during iteration, potentially leading to elements being skipped.

## Bug Description

The `pairs` iterator in Lua, when used with deeply nested tables, may exhibit unexpected behavior if modifications to the tables are performed within the iteration loop. This can manifest as some elements of the nested table not being processed by the iteration. This occurs because `pairs` works with internal indices which can change while the loop is running.

## Reproduction

The `bug.lua` file contains code that reproduces the bug.  Running this script might not always produce noticeable omissions, as the exact outcome depends on the modification process within the iteration. This makes this bug hard to detect and is usually seen as unexpected behavior.

## Solution

The `bugSolution.lua` file demonstrates a solution using a manual iterative approach to avoid this issue. The solution involves creating a copy of the table before iteration or using an alternative traversal strategy that's less sensitive to modifications during iteration.

## Contributing

Contributions are welcome. If you have other scenarios or solutions, feel free to open a pull request.