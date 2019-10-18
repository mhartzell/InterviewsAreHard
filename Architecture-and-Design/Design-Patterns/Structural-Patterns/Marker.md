# Marker

Marker provides a means to associate metadata with a class where the language does not have explicit support for such metadata.  A class implements a marker interface (also called tagging interface), and methods that interact with instances of that class test for the existence of the interface. Whereas a typical interface specifies functionality (in the form of method declarations) that an implementing class must support, a marker interface need not do so. The mere presence of such an interface indicates specific behavior on the part of the implementing class.

C# implements this pattern through custom attributes.