# Single-Responsibility Principle

**A class should have one, and only one, reason to change.** 

Every module or class should have responsibility over a single part of the functionality provided by the software, and that responsibility should be entirely encapsulated by the class.  A change in responsibility requires a class to change, which may break existing functionality. Additionally, when a class has multiple responsibilities, changes to one set of responsibilities could break other responsibilities.  Therefore, classes should be small, simple and highly specific, leading toward a more cohesive design.

It's worth noting that the level of granularity for class responsibility is subjective and influenced by the problem domain.

