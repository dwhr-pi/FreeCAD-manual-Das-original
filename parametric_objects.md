## Parametric objects

FreeCAD is designed for parametric modeling. This means that the geometry that you create, instead of being
freely sculptable, is produced by rules and parameters. For example, a cylinder might be produced from a
radius and a height. With these two parameters, the program has enough information to build the cylinder.

Parametric objects, in FreeCAD, are in reality small pieces of program, that run whenever one of the
parameters has changed, in order to recompute the shape of the object. Objects can have a lot of different
kinds of parameters: numbers (integers like 1, 2, 3 or floating-point values like 3.1416), real-world sizes
(1mm, 2.4m, 4.5ft), (x,y,z) coordinates, or even another object.

For example, a Pad object takes a 2D shape and an extrusion distance. With these, it produces an extrusion (pad)
of the given 2D shape, by the given distance. You can then use this pad as a base for further operations, such as
subtractions (pocket), until arriving at your final object. All the intermediary operations (2D shape, pad,
pocket, etc) are still there, and you can still change any of their parameters anytime. The whole chain will 
be rebuilt (recomputed).

![parametric_modeling](http://www.freecadweb.org/wiki/images/4/47/Parametric_objects.jpg)

Two important things are necessary to know:

1. Recomputation is not always automatic. Heavy operations, that might modify a big portion of your document, and therefore take some time, are not performed automatically. Instead, the object (and all the objects that depend on it) will be marked for recomputation (a small blue icon appears on them in the tree view). You must then press the recompute button to have all the marked objects recomputed.
2. The dependency tree must always flow in the same direction. Loops are forbidden. You can have object A which depends on object B which depend on object C. But you cannot have object A which depends on object B which depends on object A. That would be a circular dependency. However, you can have many objects that depend ona same object, for example objects B and C both depend on A.

**Read more**

* The properties editor: http://www.freecadweb.org/wiki/index.php?title=Property_editor