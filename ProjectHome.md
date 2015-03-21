python-javaobj is a python library that provides functions for reading (writing is WIP) of Java objects
serialized or will be deserialized by ObjectOutputStream. This form of object
representation is a standard data interchange format in Java world.

javaobj module exposes an API familiar to users of the standard library marshal, pickle and json modules.

## Features ##

  * Java object instance unmarshaling
  * Java class itself unmarshaling
  * Primitive values unmarshaling
  * Automatic conversion of Java Collections to python ones (HashMap => dict, ArrayList => list, etc)

## Requirements ##

  * Python >= 2.6

## Usage ##

Unmarshalling of Java serialised object:

```
import javaobj

jobj = self.read_file("obj5.ser")
pobj = javaobj.loads(jobj)
print pobj
```

Or, you can use Unmarshaller object directly:

```
import javaobj

marshaller = javaobj.JavaObjectUnmarshaller(open("sunExample.ser"))
pobj = marshaller.readObject()

self.assertEqual(pobj.value, 17)
self.assertTrue(pobj.next)

pobj = marshaller.readObject()
```