# Lua pairs iterator unexpected behavior

This repository demonstrates a potential issue with Lua's `pairs` iterator when dealing with nested tables and modifications during iteration.

The `bug.lua` file contains code that recursively iterates through a nested table.  Under certain conditions (especially when modifying the table during iteration), the `pairs` iterator may skip elements or even cause an infinite loop. This is because `pairs` creates an iterator that depends on the internal structure of the table which can be altered by modifications during the iteration.

The `bugSolution.lua` file offers a safer alternative approach which may mitigate this behavior in many cases. Note that completely avoiding issues may require a different table traversal strategy depending on the use case.